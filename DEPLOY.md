# Deploy — Reddit Brasil landing

## Onde está
- **Repo (público):** https://github.com/aondaai/reddit-brasil-site  (auto-deploy no push p/ `main`)
- **Render static site:** `reddit-brasil-site` · id `srv-d8vt09sm0tmc73d781qg`
- **Preview:** https://reddit-brasil-site.onrender.com
- **Produção:** https://redditbrazil.com · https://redditbrazil.com.br (os dois servem o mesmo site; `www` redireciona pro apex)

## DNS (GoDaddy) — aplicado nos dois domínios
| Tipo | Nome | Valor | TTL |
|---|---|---|---|
| A | @ | 216.24.57.1 | 600 |
| CNAME | www | reddit-brasil-site.onrender.com | 600 |

SSL: emitido automaticamente pelo Render após verificação.

## Como atualizar a página
Edite `site/index.html` e me peça (ou rode):
```bash
cd "/Users/angeloorru/Documents/Claude/Projects/Agencia Reddit Brasil/site"
git add index.html && git commit -m "update" && git push
```
O Render faz o deploy sozinho.

## Páginas & estrutura
- `/` — `index.html` (home: hero, serviços, método, por que Reddit, planos, contato)
- `/reddit-seo-geo/` — serviço flagship SEO & GEO/AEO
- `/reddit-ads/` — serviço Reddit Ads
- `/blog/quanto-custa-anunciar-no-reddit/` — post âncora (custo de Reddit Ads)
- `sitemap.xml` · `robots.txt` · `favicon.svg` · `og-image.png`

URLs limpas (sem `.html`) via pastas com `index.html`. Cada página tem `<title>`,
meta description, canonical, Open Graph e JSON-LD (`Organization`/`Service`/`FAQPage`/`BlogPosting`).
SEO/AEO: H2 em formato de pergunta + `FAQPage` para citação por IA.

> Nota de credibilidade: números específicos do Brasil (DAU pt-BR, CPC em BRL) devem ser
> validados com fonte primária / campanha-teste antes de publicar. Não usar número US como BR.

## Pendências
- **Formulário de contato** aponta para `contato@redditbrazil.com` (placeholder via mailto).
  Criar essa caixa de e-mail OU trocar por outro endereço / Formspree / back-end.
- **Rotacionar as chaves** (GoDaddy API key/secret e Render API key) — foram compartilhadas em chat.
