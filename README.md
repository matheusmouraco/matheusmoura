# Matheus Moura — Landing Page · Método Tração

Landing page de marca pessoal de alta performance. HTML estático único, sem build, sem dependências de runtime — abre em qualquer lugar e publica em qualquer host estático.

```
matheus-moura-site/
├── index.html            ← o site inteiro (HTML + CSS + JS inline)
├── site.webmanifest      ← PWA / ícones
├── robots.txt            ← libera buscadores + bots de IA (GEO)
├── sitemap.xml           ← mapa do site
└── assets/
    ├── fonts/            ← Geist + Geist Mono (self-hosted, .woff2)
    ├── avatar-ring.png   ← sua foto com o anel gradiente
    ├── verified.png      ← selo verificado
    ├── mark-arrow.*      ← seu ícone de marca (seta) isolado
    ├── brand-mark.webp   ← ícone original
    ├── logo-banner.png   ← seu banner @matheusmoura.co
    ├── og-image.jpg/png  ← card de compartilhamento (1200×630)
    └── icon-*.png, favicon.ico, apple-touch-icon.png
```

## Rodar localmente

```bash
cd matheus-moura-site
python3 -m http.server 4321
# abre http://localhost:4321
```

## Publicar (escolha um)

- **Vercel:** arraste a pasta em vercel.com, ou `npx vercel --prod`. Domínio grátis `.vercel.app`.
- **Netlify:** arraste a pasta em app.netlify.com/drop.
- **Cloudflare Pages / GitHub Pages:** suba a pasta como site estático.

Tudo é estático: zero configuração de servidor.

---

## ⚠️ O que personalizar antes de ir ao ar

Tudo abaixo está marcado e fácil de achar no `index.html`.

### 1. Domínio (busca e substitui)
Troque `https://matheusmoura.co/` pelo seu domínio final em **todo** o arquivo
(`index.html`, `sitemap.xml`, `robots.txt`). Afeta canonical, Open Graph, Twitter e os dados estruturados.

### 2. Cases — seção **Provas** (`id="provas"`)
Os 2 cards usam dados reais do Social Blade (jun/2026): **@gnascimento** (Deputado Federal — 216 mil seguidores, +152 mil em 30 dias) e **@gilbertonjr** (Vereador 3x SP — 270 mil, +87 mil em 30 dias). Confira se os números batem com a realidade dos perfis antes de publicar e atualize quando quiser (o Social Blade muda com o tempo).

### 3. Oferta — seção **Mentoria** (`id="mentoria"`)
O preço foi removido da página (a venda acontece no diagnóstico). O card mostra o pacote, a garantia de risco invertido (atrelada à **aplicação**) e leva ao "Agendar diagnóstico". Se quiser exibir preço de novo, é só pedir.

### 4. Botões de contato
Hoje os CTAs **"Agendar diagnóstico"** e **"Pegar a Arrancada"** apontam para o Instagram `@matheusmoura.co`. Se você usa WhatsApp ou Calendly, troque os `href`:
- WhatsApp: `https://wa.me/55SEUNUMERO`
- Calendly: seu link de agenda

### 5. Chips do "Sobre"
Estão como "Mandatos públicos · Autoridades · Negócios premium". Ajuste se quiser refletir outros tipos de cliente.

### 6. Upgrade opcional do hero
A foto do puff (a de estúdio que você colou no chat) ficaria ótima como fundo do hero. Salve-a em `assets/hero.jpg` e me chame que eu integro com tratamento e overlay.

---

## O que já está pronto (nível elite)

**Design** — identidade Método Tração: preto `#0D0D0D` + off-white `#F5F1EA` + laranja `#FF4D00`; tipografia Geist (grotesca premium, estilo Stripe/Linear) + Geist Mono (técnico); títulos em caixa-baixa com tracking apertado, laranja dosado, glass/frosted nos painéis, orbs de atmosfera, cockpit de marchas, reveals em scroll, grão e textura diagonal.

**SEO técnico** — title + meta description otimizados, canonical, Open Graph + Twitter Card com og-image dedicada, favicons completos, `sitemap.xml`, `robots.txt`, `lang="pt-BR"`, HTML semântico, hierarquia de headings, `alt` em imagens.

**GEO (otimização para IA)** — dados estruturados JSON-LD (`Person`, `Service`, `WebSite`, `FAQPage`), `robots.txt` liberando GPTBot, PerplexityBot, ClaudeBot, Google-Extended e afins, FAQ em linguagem natural e citável, definições claras do que é o Método Tração.

**Performance / Core Web Vitals** — CSS e JS inline (sem render-block externo), fontes self-hosted `.woff2` com `preload` + `font-display:swap`, imagens com `width`/`height` (sem CLS) e `loading="lazy"` abaixo da dobra, JavaScript vanilla mínimo, zero dependências.

**Acessibilidade** — skip link, `:focus-visible`, `aria` no menu e FAQ, `prefers-reduced-motion` respeitado, navegação por teclado.

---

## Próximos passos GEO (rodam fora da página)

A página já cobre o GEO técnico do guia (robots com todos os bots de IA, schema de identidade, FAQ com texto schema = texto visível, H1 único, HTML semântico). O que falta é **fora do código** e potencializa a citação por IA:

1. **Consistência NAP / `sameAs`** — deixe nome, descrição e contato **idênticos** no site, no Instagram (@matheusmoura.co) e no Google Business. A IA cruza as fontes; divergência derruba a confiança.
2. **Conteúdo citável (formato resposta-primeiro)** — quando quiser escalar, crie páginas/artigos onde cada subtítulo é uma pergunta e a primeira frase já responde (ex.: "Como crescer um perfil de [médico] no Instagram?"). É o que a IA extrai e cita. Posso construir essas páginas depois.
3. **Validar pós-publicação** — com o site no ar, rode a home no [Rich Results Test](https://search.google.com/test/rich-results) e no [validator.schema.org](https://validator.schema.org), e cadastre no Google Search Console enviando o `sitemap.xml`.

> As IAs levam semanas para re-rastrear. A fundação está pronta; os resultados aparecem conforme os robôs voltam e encontram a entidade clara.

## Área do cliente (manuais)

Páginas internas que você entrega aos clientes da mentoria, em `/manual/`:

- **`/manual/`** — central de recursos (índice dos manuais)
- **`/manual/template-bio.html`** — Template de Bio **interativo**: contador de 150 caracteres ao vivo, preview da bio montada e botão copiar. Salva no navegador do cliente automaticamente.

Compartilhe o link direto com seus clientes (ex.: `matheusmoura.co/manual/template-bio.html`). As páginas usam `noindex` (não aparecem no Google) por serem entregáveis — remova `<meta name="robots" content="noindex...">` se quiser torná-las públicas para tráfego orgânico.

**Adicionar um novo manual:** duplique `manual/template-bio.html`, troque o conteúdo, e no índice (`manual/index.html`) mude o card de "Em breve" para "Disponível" com o link. Já deixei 3 cards de exemplo prontos (Ganchos, Calendário, Posicionamento). Todos usam o estilo compartilhado `assets/manual.css`.

---

*Identidade e conteúdo baseados no Método Tração. "A maioria acelera. Quase ninguém ganha tração."*
