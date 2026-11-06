# cacus-site

Página institucional da Cacus Pet (cacuspet.com.br) e o **Blog da Cacus** (cacuspet.com.br/blog), publicados via GitHub Pages a partir da branch `main`.

- `index.html` — página institucional (HTML puro, sem build).
- `blog/`, `_posts/`, `_layouts/`, `_includes/`, `_config.yml` — blog em Jekyll (o GitHub Pages compila sozinho a cada push).
- `assets/cacus-symbol.png` — símbolo oficial da marca (não alterar).

## Como publicar um post

1. Crie um arquivo em `_posts/` com o nome `AAAA-MM-DD-titulo-em-minusculas-sem-acento.md`.
2. Comece com o cabeçalho:

   ```
   ---
   title: "Título do post"
   description: "Uma frase que resume o post (aparece no Google e na lista)."
   publico: tutores        # tutores | profissionais | novidades
   author: "Cacus Pet"     # opcional; padrão "Cacus Pet"
   revisao: ""             # opcional, ex.: "Amanda Marson, médica veterinária"
   ---
   ```

3. Escreva o texto em Markdown abaixo do cabeçalho. Use `##` para seções; sem `#` de título (o layout já põe).
4. Abra um pull request. Depois do merge em `main`, o post entra no ar em 1–2 minutos.

## Medição (#41)

- Umami Cloud (sem cookies, dispensa banner) no `_includes/head.html` e no `index.html`; o mesmo ID vale para todos os endereços da Cacus e o painel separa por hostname. O `data-domains` impede contar `localhost` e prévias.
- Eventos do site: `site-cta-care-lista`, `site-cta-pro-lista`, `site-cta-store`, `site-cta-entrar`, `site-cta-blog-lista`, `site-cta-fundadores` (atributo `data-umami-event`) e `site-lista-enviada` (propriedade `perfil` = tutor/veterinario/clinica). Nunca mandar nome, e-mail ou id em evento ou URL.
- `sitemap.xml` e `robots.txt` saem do plugin `jekyll-sitemap`; páginas de redirecionamento e de confirmação usam `sitemap: false` e `noindex`.

## Regras de conteúdo

- Português do Brasil, direto, sem jargão. Marca sempre "Cacus" (nunca "Cacús"); o assistente é "o Cacus".
- Posts para tutores e profissionais recebem automaticamente o aviso "não substitui a consulta veterinária". Nunca recomendar dose, remédio ou tratamento específico.
- Não citar a cidade da sede. Não divulgar o número de vagas do programa de clínicas fundadoras ("restam poucas vagas" é o máximo).
- Links para produtos (beta fechado): Care e Pro entram pela lista de espera, `/lista-de-espera/?perfil=tutor&interesse=care` (tutor) e `/lista-de-espera/?perfil=vet&interesse=pro` (profissional), sempre com `utm_source`/`utm_medium`/`utm_campaign`; o programa de fundadores segue em `https://pro.cacuspet.com.br/fundadores`; Store `https://cacuspetstore.com.br`. O único link para o login do Care é o "Entrar" do cabeçalho ("Já tem convite?"), para quem já foi convidado. O layout já coloca a chamada final conforme o `publico`.
- Imagens: só com direito de uso; salvar em `assets/blog/` e referenciar com caminho absoluto (`/assets/blog/arquivo.jpg`).
