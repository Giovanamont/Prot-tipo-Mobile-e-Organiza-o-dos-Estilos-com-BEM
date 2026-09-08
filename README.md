# Protótipo Mobile e Organização dos Estilos com BEM

Atividade da disciplina de Desenvolvimento Mobile: elaboração das telas mobile em baixa fidelidade do projeto **Habit** (blog de conteúdos organizados por categorias) e organização inicial dos estilos CSS com o padrão **BEM**, preparando a base para a futura implementação dos componentes em React.

## Integrantes do grupo

- Giovana Monteiro
- Guilherme Andrade
- Reigieli

## Sobre a aplicação

O fluxo geral parte da página inicial (Home) e se ramifica em três frentes principais:

- **Fluxo público**: Home → Categoria → Destaques → Busca → Newsletter
- **Fluxo de autenticação**: Login → Cadastro → Perfil
- **Fluxo administrativo**: Categorias → Criar Post → Fila de Revisão → Fila de Comentários → Usuários → Escolhas do Editor

## Telas elaboradas

As 14 telas mobile em baixa fidelidade estão na pasta [`/wireframes`](./wireframes):

| Tela | Arquivo | Descrição |
|---|---|---|
| tela_01 | `wireframes/tela_1.png` | Home — ponto de entrada da aplicação (categorias populares, destaques, escolhas do editor) |
| tela_02 | `wireframes/tela_2.png` | Postagens de uma categoria selecionada |
| tela_03 | `wireframes/tela_3.png` | Área de destaques |
| tela_04 | `wireframes/tela_4.png` | Assinatura da newsletter |
| tela_05 | `wireframes/tela_5.png` | Admin — administração de categorias |
| tela_06 | `wireframes/tela_6.png` | Admin — criação de postagem |
| tela_07 | `wireframes/tela_7.png` | Admin — escolhas do editor |
| tela_08 | `wireframes/tela_8.png` | Admin — gerenciamento de usuários |
| tela_09 | `wireframes/tela_9.png` | Admin — fila de revisão de postagens |
| tela_10 | `wireframes/tela_10.png` | Admin — fila de moderação de comentários |
| tela_11 | `wireframes/tela_11.png` | Resultados de busca |
| tela_12 | `wireframes/tela_12.png` | Login / autenticação |
| tela_13 | `wireframes/tela_13.png` | Criação de conta |
| tela_14 | `wireframes/tela_14.png` | Perfil do usuário |

Também há protótipos em HTML/CSS de cada tela na pasta [`/telas`](./telas), usados como referência intermediária para a extração dos estilos.

## Componentes identificados e variações

| Componente | Bloco BEM | Onde aparece | Variações |
|---|---|---|---|
| Navegação (header) | `.navigation` | Todas as telas públicas | única (logo, links, busca, entrar) |
| Menu lateral (admin) | `.menu` | Todas as telas administrativas (05–10) | única |
| Hero / banner de destaque | `.hero` | Home | padrão |
| Card de post em destaque | `.hero__card`, `.featured-posts__item` | Home, Busca | padrão |
| Card de post em grade | `.post-grid__item` | Categoria, Destaques | padrão |
| Card de categoria | `.category-highlight__item`, `.category-filter__item` | Home | destaque, filtro (com estado `--active`) |
| Botão (Button) | `.button` | Todas as telas | `--primary`, `--outline` |
| Abas de ordenação | `.sort-tabs__item` | Categoria | padrão, `--active` |
| Formulário (Form) | `.form-card`, `.form__*` | Newsletter, Login, Cadastro | `--newsletter`, `--login`, `--cadastro` |
| Formulário de postagem | `.post-form` | Admin — Criar Post | com campo de editor (`--editor`) |
| Painel (Panel) | `.panel` | Telas administrativas | única |
| Métrica / indicador | `.metric-card` | Telas administrativas | única |
| Tabela (Table) | `.table-content` | Admin — categorias, usuários, filas | uso genérico para listas de registros |
| Rodapé (Footer) | `.footer`, `.site-footer` | Todas as telas públicas | única |
| Imagem de card | `.card-image` | Cards em geral | `__perfil` (imagem circular/maior do perfil) |


## Organização dos arquivos

```
projeto-mobile/
├── wireframes/     → telas mobile em baixa fidelidade (PNG), uma por tela
├── telas/          → protótipos HTML das telas, usados de referência para os estilos
├── css/            → estilos organizados por responsabilidade, seguindo o padrão BEM
│   ├── variables.css     → reset e definições globais (cor, tipografia, box-sizing)
│   ├── navigation.css    → barra de navegação / cabeçalho
│   ├── menu.css          → menu lateral da área administrativa
│   ├── card.css          → hero, cards de destaque e de perfil
│   ├── button.css        → botões e suas variações
│   ├── form.css          → formulários (newsletter, login, cadastro)
│   ├── post-form.css     → formulário de criação de postagem
│   ├── category.css      → categorias em destaque e filtro de categorias
│   ├── category-page.css → cabeçalho de categoria, abas de ordenação e grid de posts
│   ├── content.css       → colunas de conteúdo, postagens em destaque, escolhas do editor
│   ├── image.css         → imagens usadas dentro dos cards
│   ├── panel.css         → painéis da área administrativa
│   ├── metric.css        → cards de indicadores (métricas)
│   ├── table.css         → tabelas de registros da área administrativa
│   ├── admin.css         → grid geral da área administrativa (menu + conteúdo)
│   └── footer.css        → rodapé
└── README.md
```

Cada arquivo CSS reúne os estilos de um componente ou de um grupo de componentes relacionados, seguindo o padrão **BEM (Block, Element, Modifier)**:

- **Bloco** — componente independente (ex.: `.card`, `.button`, `.form`);
- **Elemento** — parte pertencente ao bloco (ex.: `.hero__title`, `.form__input`);
- **Modificador** — variação do bloco ou do elemento (ex.: `.button--primary`, `.category-filter__item--active`).

## Referência das telas

As telas mobile em baixa fidelidade podem ser consultadas diretamente na pasta [`/wireframes`](./wireframes) deste repositório.