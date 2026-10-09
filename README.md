# kiptv-site

Site público do **kIPTV** (GitHub Pages): página inicial, política de privacidade e suporte, em pt-BR, en e es.
O código do app fica num repositório privado. Este repositório tem só HTML/CSS estático (ADR-0011, SDD-12 §8.4).

- Sem etapa de build, sem JavaScript e sem requisições a terceiros (nem Google Fonts nem analytics). A página de privacidade não pode contradizer a si mesma.
- `review.m3u`: streams de amostra só para a App Review (citada nas notas da revisão; não é linkada nas páginas).
- URLs usadas no App Store Connect:
  - Marketing: `https://maiconkeller.github.io/kiptv-site/`
  - Suporte: `https://maiconkeller.github.io/kiptv-site/support.html`
  - Privacidade: `https://maiconkeller.github.io/kiptv-site/privacy.html`

## Publicar
1. Crie o repositório **público** `maiconkeller/kiptv-site` e envie estes arquivos para a branch `main`.
2. Em *Settings → Pages*: *Source* = *Deploy from a branch*, branch `main`, pasta `/ (root)`.
3. Aguarde o primeiro deploy e abra as 3 URLs acima no iPhone e no Mac (modo claro e escuro).

## E-mail de suporte
`maiconkeller@outlook.com` (pessoal, por enquanto). Para trocar: `grep -rl maiconkeller@outlook.com . | xargs sed -i '' 's/maiconkeller@outlook.com/novo@exemplo.com/g'`.

## Fonte Sora (opcional)
O logotipo em texto usa a Sora ExtraBold se o arquivo `fonts/Sora-ExtraBold.woff2` existir; caso contrário, a fonte do sistema.
A Sora está sob a SIL Open Font License 1.1, que permite hospedá-la aqui. Se adicionar o arquivo, inclua também `fonts/OFL.txt`.
Não use o Google Fonts: ele envia o IP do visitante ao Google, o que destoa da política de privacidade.

## Manutenção
- `privacy.html` segue o texto normativo do SDD-12 §8.4. Mudou o comportamento de rede ou de dados do app? Atualize a página, a **data de vigência** e revise o rótulo de privacidade no App Store Connect (SDD-12 §8.5).
- As mensagens de erro citadas em `support.html` são cópias das strings do app (`Localizable.xcstrings`). Se mudarem no app, atualize aqui.
- Idiomas: pt-BR (principal), en e es. Cada página tem os três idiomas (em `privacy.html` e `support.html`: `#pt`, `#en`, `#es`); mudou uma, mude as três. As citações de botões e mensagens seguem as strings do app em cada idioma.
- Nunca cite nomes de emissoras, serviços de streaming ou listas de terceiros neste site.
