# GastOS

Finanças pessoais, do casal ou da casa — para **Windows**, **Android** e **celular (PWA)**.
Cada pessoa cadastra só o que é dela (renda, contas, cartões, VR/VA, investimentos, metas) e a aba **Casa** soma tudo depois da sincronização.

> Desenvolvido por Mica.

## O que ele faz
- **Passo a passo inicial**: renda (fixa, variável ou as duas), rendas fixas com data de pagamento (inclui *5º dia útil*), contas bancárias (saldo pode ser negativo / cheque especial), cartões e limites, VR/VA, investimentos, metas com projeção, contas fixas e parcelas, faturas dos cartões.
- **Painel individual** e aba **Casa** (soma de todas as pessoas).
- Lançamento rápido de despesas e proventos, com ícones, recorrência, parcelas e forma de pagamento (PIX, VR, VA, cartão).
- Histórico editável, fluxo de caixa, avisos de contas a vencer, investimento (% da renda) e metas.
- Funciona **sem internet**; os dados ficam no próprio aparelho.
- **Sincronização** (opcional) entre aparelhos: servidor próprio com dados criptografados, Google Drive, arquivo ou pasta compartilhada.

## Baixar
Os programas prontos ficam em **Releases** (instalador e versão portátil do Windows, APK do Android e servidor para PC).

## Estrutura
```
src/index.html        o app inteiro (fonte única)
tools/                gera as variantes (desktop, web, android) a partir do src
desktop/              programa de Windows (Electron)
android/              app Android (WebView) + build sem Android Studio
web/                  PWA (manifest, service worker, ícones)
server/               servidor de sincronização (Deno, Cloudflare, Node)
docs/                 guias (Google, nuvem, servidor no PC, APK, celular)
.github/workflows/    gera os programas automaticamente no GitHub
```

## Rodar e gerar localmente
```bash
node tools/build-variants.js        # gera desktop/index.html, web/index.html e android/assets/index.html
cd desktop && npm install && npm start      # abre o app de computador
cd desktop && npm run build                  # instalador + portátil (rode no Windows)
sh android/build-apk.sh                      # APK (Linux; veja os pacotes no topo do script)
```
Abrir `web/index.html` num servidor estático (https) já funciona como PWA.



## Licença
MIT — veja `LICENSE`. Avisos de terceiros (fonte Inter, Electron…) em `THIRD-PARTY-NOTICES.md`.
