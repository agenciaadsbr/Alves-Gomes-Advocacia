# LP Indenização — Alves Gomes Advocacia

Landing page de captação para **Direito Cível / Indenização por Danos Morais e Materiais**, do escritório Alves Gomes Advocacia e Consultoria (Londrina/PR).

## Arquivos

- **`index.html`** — a página principal. Autocontida: toda imagem (logo, fotos) está embutida em base64 dentro do próprio arquivo, então não depende de nenhum outro asset para funcionar.
- **`redirect.html`** — página de transição pós-formulário. Recebe `nome` e `whatsapp` por query string, espera ~3s e redireciona para o WhatsApp do escritório (`5543991919159`) com uma mensagem já personalizada.

Não há pasta `assets/` — as duas páginas funcionam sozinhas, em qualquer lugar, sem mais nada ao lado.

## Publicar

### Opção A — GitHub Pages
1. Suba os dois arquivos na raiz do repositório (ou numa subpasta, ex. `indenizacao/`).
2. Em **Settings → Pages**, aponte para a branch/pasta onde estão os arquivos.
3. A URL final fica algo como `https://<usuario>.github.io/<repo>/` (ou `/indenizacao/` se estiver em subpasta).

### Opção B — Embed via iframe no WordPress (padrão já usado noutros projetos da ADS BR)
1. Hospede os dois arquivos em algum lugar com URL pública (GitHub Pages, Vercel, etc.).
2. No Elementor, crie a página em `alvesgomes.com.br/indenizacao/` e insira um bloco de HTML/iframe apontando para a URL do `index.html` publicado.
3. Confirme que o site de destino não bloqueia embed via `X-Frame-Options` (já houve esse problema noutro projeto — se a página ficar em branco dentro do iframe, é essa a causa mais provável).

## Pendências antes de publicar de verdade

1. **Armazenamento de lead** — o formulário hoje só faz uma tentativa silenciosa de `fetch('/api/leads', ...)` (função `registerLead()`, perto do fim do `index.html`) que falha sem travar o redirecionamento. Isso precisa apontar para onde vocês querem guardar o lead (Supabase, planilha, CRM). Sem isso, o formulário funciona (leva pro WhatsApp), mas nenhum lead fica registrado em lugar nenhum.
2. **Imagens** — duas fotos usadas na página (hero e background da seção de contato) são de banco de imagens em resolução relativamente baixa (626px de largura); se quiserem mais nitidez, vale trocar por versões em maior resolução ou fotos reais do escritório.
3. **Domínio/DNS** — nada configurado aqui; é só o código da página.

## Números e contatos usados na página

- WhatsApp: **(43) 99191-9159** (`5543991919159`)
- E-mail: contato@alvesgomes.com.br
- Endereço: Av. Higienópolis, 32, Sala 703, Ed. Newton Câmara, Centro, Londrina/PR
