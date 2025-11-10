## Instruções rápidas para agentes de código (projeto: site estático)

Resumo curto
- Repositório pequeno com site estático (HTML/CSS) entregue em arquivos simples.
- Arquivos principais: `vaitomando.html`, `reposiva.html`, `estilos/style.css`, diretórios `fontes/` e `imagens/`.

O que é importante saber
- Não existe sistema de build, package.json ou servidor; mudanças são validadas abrindo os HTML no navegador.
- A tipografia inclui uma fonte local em `fontes/idroid.otf` (declarada em `estilos/style.css` via @font-face).
- Imagens referenciadas por caminhos relativos em `imagens/` — preserve nomes e extensões quando substituir arquivos.

Padrões e convenções do projeto
- CSS centralizado em `estilos/style.css`. Use as variáveis :root (por exemplo `--cor1`, `--fonte-android`) ao adicionar cores ou fontes para manter consistência.
- Estrutura de pages: cada HTML é autônomo; não há templates. Ao criar novas páginas, siga a mesma hierarquia de pastas e links relativos (por exemplo `link rel="stylesheet" href="estilos/style.css"`).
- Evite alteração global de nomes de pastas/paths (por exemplo `imagens/`, `estilos/`, `fontes/`) sem atualizar todos os HTML.

Casos comuns e exemplos concretos
- Para adicionar uma imagem responsiva em `vaitomando.html`, use <picture> com `srcset` apontando para arquivos em `imagens/` (veja exemplos existentes: `irina-blok.jpg` / `irina-blok-pq.jpg`).
- Para adicionar uma nova seção de destaque, reutilize as variáveis CSS e a fonte `--fonte-android` para títulos (veja `main h1` em `estilos/style.css`).
- Para testes de responsividade, abra `reposiva.html` ou redimensione o navegador com DevTools.

Regras ao modificar o repositório
- Preserve o encoding UTF-8; os arquivos usam português e acentuação. Mantenha o `@charset "UTF-8"` em `style.css`.
- Ao alterar `style.css`, mantenha a ordem lógica (variáveis :root, reset básico, depois regras de layout). Evite reformatar todo o arquivo.

Como validar mudanças localmente
1. Salve arquivos.
2. Abra os HTML no navegador (duplo-clique em `vaitomando.html` ou `reposiva.html`).
3. Para inspeção rápida: abra DevTools (F12) e verifique console e responsividade.

O que não está presente (limitações detectáveis)
- Não há testes automatizados, bundlers, ou pipeline CI detectáveis no repositório.
- Dependências externas limitam-se a Google Fonts import em `style.css` e embed de YouTube em `vaitomando.html`.

Se você for editar o repositório, foque em
- Manter paths relativos e a hierarquia `estilos/`, `imagens/`, `fontes/`.
- Seguir as variáveis CSS para consistência visual.
- Testar visualmente no navegador e checar console do DevTools para erros de carregamento (404 de imagens/fontes).

Perguntas para o mantenedor
- Deseja que eu padronize meta tags ou adicionar um README com passos de contribuição?

Fim.
