# Guia Prático - UF 1.1 (Aula 3)

## Git e GitHub + Imagens e Atributos: Guardar a História do Projeto 🐙

- **Objetivo:** Perceber o que é o controlo de versões, configurar o Git e usar `init`, `status`, `add`, `commit` e `log`, publicar o projeto no GitHub com `push` e, na segunda metade, usar atributos e novos elementos (`img`, `abbr`, `span`, `blockquote`, `div`) para dar ao vosso **portefólio** uma fotografia e um testemunho.

> 📖 **Como estudar com este guia:** este guia tem os mesmos passos que fizemos na aula, pela mesma ordem. Sigam as Partes e os Passos **por ordem**, no vosso computador, e escrevam o código e os comandos **à mão** (não copiem e colem). No fim de cada etapa há uma caixa **✅ Confirmem antes de avançar**: só passem à frente quando o vosso resultado for igual ao que lá está. Se algo não funcionar, vejam a secção **🆘 Se Algo Correr Mal**, no fim do guia.

> 💡 **Mac:** sempre que aparecer a tecla **Ctrl**, usem a tecla **Cmd (⌘)**.

> 🔙 **Ponto de partida:** a pasta `portefolio` com o `index.html` da aula 2 (se faltaram, copiem a pasta [`projeto/sessao-02/`](../../projeto/sessao-02/)) e uma **conta GitHub** criada (trabalho de casa da aula 2). Na Parte 4 vão precisar de uma **fotografia vossa** (de cara, com boa luz). Se não tiverem, usem a ilustração [`foto.svg`](../../projeto/sessao-03/imagens/foto.svg).

---

### Parte 1: Porquê Controlo de Versões? (Os Pontos de Gravação) 💾

Já vos aconteceu ter ficheiros assim?

```
trabalho.docx
trabalho-v2.docx
trabalho-final.docx
trabalho-final-corrigido.docx
trabalho-final-AGORA-SIM.docx
```

Ninguém sabe qual é a versão certa nem o que mudou entre elas. Os programadores resolveram este problema com o **controlo de versões**: um programa que guarda **fotografias** do projeto ao longo do tempo, com uma nota a dizer o que mudou.

#### Passo 1: Abrir o Projeto e Rever

1. Abram a pasta `portefolio` no VS Code (**File** → **Open Folder...**).
2. Abram o `index.html` com o **Live Server**.
3. Pergunta rápida, para responderem de cabeça: qual é a diferença entre o `head` e o `body`? Para que serve o `<!-- -->`? (Se não se lembrarem, revejam a aula 2.)

#### Passo 2: Git e GitHub

Pensem num **jogo de computador com pontos de gravação**. Antes de uma parte difícil, gravam o jogo. Se correr mal, voltam ao ponto gravado. O **Git** faz isto com o projeto:

- cada **ponto de gravação** chama-se **commit** (em português às vezes diz-se "confirmação", mas toda a gente usa *commit*);
- cada commit guarda o **estado de todos os ficheiros** naquele momento, **quem** o fez, **quando** e uma **mensagem** a explicar o que mudou;
- podemos ver a história toda e voltar atrás quando quisermos.

E o **GitHub**? São coisas diferentes:

1. **Git**: um programa **no vosso computador** que guarda a história do projeto.
   - Analogia: o álbum de fotografias que têm em casa.
2. **GitHub**: um **site** que guarda cópias de projetos Git na internet.
   - Analogia: um serviço na nuvem onde guardam uma cópia do álbum e a mostram a quem quiserem.

Com o GitHub, o projeto fica **seguro** (se o computador avariar, não perdem nada), podem trabalhar nele **noutro computador** e outras pessoas (o formador, colegas, futuros empregadores) podem **vê-lo**. Ao longo do curso, o vosso GitHub vai tornar-se o vosso **portefólio**.

> 💡 **Dica:** à pasta de um projeto que está a ser seguido pelo Git chama-se **repositório** (em inglês, *repository*, ou só *repo*).

---

### Parte 2: Git no Nosso Computador (O Primeiro Commit) 🐙

#### Passo 1: Orientar-se no Terminal

O Git usa-se sobretudo pelo terminal. Abram o terminal no VS Code (**Ctrl + `**). Como abriram a pasta do projeto, o terminal já está **dentro** dela. Vamos confirmar com dois comandos:

```bash
pwd
```

`pwd` (*print working directory*) responde à pergunta **"onde estou?"**. Deve aparecer um caminho que acaba em `portefolio`.

```bash
ls
```

`ls` (*list*) responde à pergunta **"o que há aqui?"**. Deve aparecer o `index.html`.

> ⚠️ **Atenção:** se o `pwd` não acabar em `portefolio`, **não continuem**. Fechem o terminal (ícone do caixote do lixo), confirmem que abriram a **pasta** do projeto no VS Code e abram um terminal novo.

#### Passo 2: Configurar o Git (Só Uma Vez por Computador)

O Git precisa de saber **quem são**, para assinar os vossos commits. Escrevam, com os **vossos** dados:

```bash
git config --global user.name "Ana Martins"
git config --global user.email "ana.martins@exemplo.pt"
```

- `git config` muda uma definição do Git.
- `--global` quer dizer "para todos os projetos deste computador". Por isso só se faz uma vez.
- Usem o **mesmo e-mail da vossa conta GitHub**, para o GitHub reconhecer os commits como vossos.

Confirmem:

```bash
git config --global --list
```

Devem aparecer as linhas `user.name=...` e `user.email=...`.

> 💡 **Dica:** o e-mail fica visível nos commits públicos. Se preferirem não o mostrar, o GitHub dá-vos um endereço privado em **Settings** → **Emails** (acaba em `@users.noreply.github.com`). Podem usar esse no `user.email`.

> ⚠️ **Atenção:** se o computador da sala for **partilhado**, repitam estes dois comandos no início de cada aula, para os commits ficarem com o vosso nome e não com o do colega.

#### Passo 3: Criar o Repositório (git init)

Primeiro, uma experiência. Escrevam:

```bash
git status
```

Aparece um erro: `fatal: not a git repository`. O Git está a dizer "esta pasta não é um repositório, não estou a seguir nada aqui". Vamos mudar isso:

```bash
git init
```

`init` (*initialize*) transforma a pasta atual num repositório. O Git cria uma pasta escondida chamada `.git`, onde guarda toda a história. **Nunca mexam nessa pasta.**

> ⚠️ **Atenção:** façam o `git init` **só dentro da pasta do projeto**. Se o fizerem por engano na pasta `Documentos` ou na pasta do utilizador, o Git passa a seguir o computador todo. Se isso acontecer, peçam ajuda ao formador para apagar a pasta `.git` criada no sítio errado.

#### Passo 4: Preparar o Commit (git status e git add)

Fazer um commit é como **enviar uma encomenda pelo correio**:

```
  Pasta de trabalho          os vossos ficheiros, como estão agora
        │
        │  git add           1. escolher o que vai na caixa
        ▼
  Área de preparação         (staging area) a caixa, ainda aberta
        │
        │  git commit        2. fechar a caixa e escrever a etiqueta
        ▼
  Repositório local          a pasta .git, com a história toda
        │
        │  git push          3. levar aos correios
        ▼
  GitHub                     a cópia na internet
```

Vejam o estado do repositório:

```bash
git status
```

O `index.html` aparece a **vermelho**, em *Untracked files* (ficheiros não seguidos): o Git vê-o, mas ainda não o está a guardar. Vamos pô-lo "na caixa":

```bash
git add index.html
git status
```

**Resultado esperado:** o `index.html` aparece agora a **verde**, em *Changes to be committed*: está na **área de preparação**, pronto para o commit.

> 💡 **Dica:** `git add .` (com um ponto) adiciona **todos** os ficheiros alterados da pasta de uma vez. É o que vamos usar quase sempre.

#### Passo 5: O Primeiro Commit

```bash
git commit -m "Estrutura base da página inicial"
```

- `commit` cria o ponto de gravação com tudo o que está na área de preparação.
- `-m` (*message*) é a mensagem, entre aspas.

**Uma boa mensagem de commit** diz, numa frase curta, **o que mudou**:

- ✅ Boas mensagens:
  - `Adiciona horário e contactos`
  - `Corrige título da secção de contactos`
  - `Estrutura base da página inicial`
- ❌ Más mensagens:
  - `alterações`
  - `asdf`
  - `versão final agora sim`

> ⚠️ **Atenção:** se se esquecerem do `-m "..."`, o Git abre um editor para escreverem a mensagem. No **Windows** abre um separador no VS Code: escrevam a mensagem na primeira linha, guardem e **fechem o separador**. No **Mac** pode abrir um editor estranho dentro do terminal: escrevam `:q!` e carreguem em **Enter** para sair, e repitam o comando com o `-m`.

#### Passo 6: Ver a História (git log)

```bash
git log
```

Aparece o vosso commit: um código comprido (o **hash**, a "impressão digital" do commit), o vosso nome, a data e a mensagem. Se o `git log` encher o ecrã, carreguem em **q** para sair.

Uma versão mais curta, com uma linha por commit:

```bash
git log --oneline
```

> ✅ **Confirmem antes de avançar:** o `git log --oneline` mostra **um** commit, mais ou menos assim (o código do início é diferente em cada computador):
>
> ```
> $ git log --oneline
> a1b2c3d (HEAD -> main) Estrutura base da página inicial
> ```

---

### Parte 3: GitHub (O Projeto na Internet) ☁️

#### Passo 1: Criar o Repositório no GitHub

1. Entrem em [github.com](https://github.com) com a vossa conta.
2. No canto superior direito, cliquem em **+** → **New repository**.
3. Preencham:
   - **Repository name:** `portefolio` (o mesmo nome da pasta);
   - **Description:** `O meu portefólio — curso de Desenvolvimento Web`;
   - **Public** (para o formador e os colegas o poderem ver).
4. **Não** ativem *Add a README file*, nem *.gitignore*, nem *license*. O repositório tem de ficar **vazio**, porque o conteúdo vem do vosso computador.
5. Cliquem em **Create repository**.

O GitHub mostra uma página com instruções. Procurem a parte **"…or push an existing repository from the command line"**.

#### Passo 2: Ligar e Enviar (git remote e git push)

Copiem os três comandos que o GitHub mostra (o endereço tem o **vosso** nome de utilizador) e corram-nos um de cada vez no terminal:

```bash
git remote add origin https://github.com/O-VOSSO-UTILIZADOR/portefolio.git
git branch -M main
git push -u origin main
```

O que faz cada um:

1. `git remote add origin URL`: diz ao vosso repositório onde fica a cópia no GitHub. `origin` é a "alcunha" desse endereço, para não termos de escrever o URL todas as vezes.
2. `git branch -M main`: garante que o ramo principal do projeto se chama `main`. Os **ramos** (*branches*) são versões paralelas do projeto: vamos usá-los na aula 14.
3. `git push -u origin main`: **envia** os commits para o GitHub (*push* = empurrar). O `-u` memoriza o destino: daqui para a frente basta escrever `git push`.

Da primeira vez, o Git pede-vos para **iniciar sessão no GitHub**. Aparece uma janela ou um aviso no VS Code: escolham **Sign in with your browser** (iniciar sessão pelo browser), entrem na vossa conta e autorizem. Depois voltem ao VS Code: o envio termina sozinho.

> ⚠️ **Atenção:** num computador **partilhado**, no fim da aula terminem a sessão do GitHub no browser.

#### Passo 3: Ver o Projeto no GitHub

Atualizem a página do repositório no GitHub. Lá está o vosso `index.html`!

- Cliquem no ficheiro para ver o código.
- Cliquem em **1 commit** (ou no ícone do relógio) para ver a história. Cliquem no commit para ver exatamente o que foi acrescentado (a verde).

> ✅ **Confirmem antes de avançar:** o vosso repositório no GitHub mostra o `index.html`. Enviem o endereço do repositório (por exemplo `https://github.com/ana-martins-dev/portefolio`) ao formador.

#### Passo 4: O Mesmo, com Cliques (o Painel Source Control)

O VS Code também sabe usar o Git. Cliquem no ícone **Source Control** na barra de atividades (o ícone com três círculos ligados, ou **Ctrl + Shift + G**).

- Os ficheiros alterados aparecem nesta lista. No Explorer, aparecem com uma letra à direita: **U** (*untracked*: novo, ainda não seguido) ou **M** (*modified*: alterado desde o último commit).
- O botão **+** ao lado de um ficheiro faz o mesmo que `git add`.
- A caixa de texto e o botão **Commit** fazem o mesmo que `git commit -m`.
- O botão **Sync Changes** / **Push** faz o mesmo que `git push`.

Nestas primeiras semanas vamos usar o **terminal**, para perceberem o que acontece em cada passo. Mais tarde podem usar o que preferirem.

#### Passo 5: O Ciclo de Trabalho

A partir de hoje, sempre que terminarem uma parte do trabalho (e **sempre no fim de cada aula**), façam este ciclo:

```bash
git status                      # 1. O que mudou?
git add .                       # 2. Pôr tudo na caixa
git commit -m "O que mudou"     # 3. Fechar a caixa com etiqueta
git push                        # 4. Enviar para o GitHub
```

> 💡 **Dica — trabalhar noutro computador (por exemplo, em casa):**
>
> - Na primeira vez, em vez de copiarem a pasta, **clonem** o repositório: `git clone https://github.com/O-VOSSO-UTILIZADOR/portefolio.git`. Isto cria a pasta com o projeto e a história toda.
> - Daí em diante, **antes de começarem a trabalhar**, escrevam `git pull` (*puxar*) para trazer as alterações feitas no outro computador. No fim, o ciclo de sempre, com `git push`.

---

### Parte 4: Atributos e Novos Elementos (A Fotografia e o Testemunho) 🖼️

#### Passo 1: Atributos (Revisão e Regras)

Na aula 2 usámos dois atributos: `lang` e `charset`. Hoje vamos usar muitos mais. As regras de escrita são sempre as mesmas:

```
<img src="imagens/foto.svg" alt="Fotografia da Ana" width="160" />
 └┬┘ └─────────┬──────────┘ └──────────┬──────────┘ └────┬────┘
 tag     atributo src            atributo alt      atributo width
```

Cada atributo escreve-se `nome="valor"`, separado dos outros por espaços, sempre na tag de abertura.

1. Nome do atributo em **minúsculas**.
2. Valor **entre aspas** (`"`).
3. Vários atributos separados por **espaços**; a ordem não interessa.

Alguns atributos podem ir em **qualquer** elemento (chamam-se **atributos globais**), como `lang` e `title`. Outros só servem para certos elementos, como o `src` e o `alt` das imagens.

#### Passo 2: Imagens (img)

**1. Arrumar a imagem no projeto.** No Explorer do VS Code, criem uma pasta nova chamada `imagens` (ícone **New Folder**). Arrastem para dentro dela a vossa fotografia e mudem-lhe o nome para `foto.jpg` (ou `foto.png`, conforme a extensão). Se não tiverem fotografia, usem a ilustração `foto.svg`.

```
portefolio/
├── imagens/
│   └── foto.svg      (ou foto.jpg)
└── index.html
```

> 💡 **Dica:** o formato **SVG** é uma imagem "desenhada com código": formas, cores e texto. Por isso fica nítida em qualquer tamanho. As fotografias costumam ser **JPG** ou **WebP**. Vamos falar de formatos na aula 11.

**2. Inserir a imagem.** Logo a seguir a `<!-- Apresentação -->`, **antes** do `h1`, escrevam:

```html
    <img
      src="imagens/foto.svg"
      alt="Ilustração do rosto de Ana Martins, a sorrir"
      width="160"
      height="160"
    />
```

Escrevam tudo numa linha; quando guardarem, o Prettier arruma os atributos um por linha, como acima, porque a linha ficou comprida. Se usarem uma fotografia vossa, o `src` é `imagens/foto.jpg` e o `alt` descreve-vos a vocês (por exemplo, `Fotografia de Rita Lopes, a sorrir`).

O que faz cada atributo:

1. `src` (*source*, origem): **onde está** o ficheiro da imagem. `imagens/foto.svg` quer dizer "dentro da pasta `imagens`, o ficheiro `foto.svg`". Vamos estudar estes **caminhos** a fundo na aula 5.
2. `alt`: o **texto alternativo**, que descreve a imagem para quem não a consegue ver.
3. `width` e `height`: largura e altura, em píxeis. Ajudam o browser a reservar o espaço certo antes de a imagem carregar. O tamanho final vai ser controlado com CSS.

O `<img>` é um **elemento vazio**: não tem conteúdo nem tag de fecho.

**Resultado esperado:** a fotografia aparece por cima do vosso nome.

> ⚠️ **Atenção:** se a vossa fotografia não for quadrada, com `width="160"` e `height="160"` fica esticada ou espalmada. Por agora, escolham uma fotografia quadrada (ou cortem-na antes) ou usem só o `width`; na aula 9 vamos acertar isto com CSS.

**3. O texto alternativo (`alt`) é obrigatório.** Quem precisa dele?

- Pessoas **cegas**: o leitor de ecrã lê o `alt` em voz alta.
- Toda a gente, quando a imagem **não carrega** (rede lenta, ficheiro em falta).
- O **Google**, que não "vê" imagens e usa o `alt` para perceber o que mostram.

Exemplos de bons e maus `alt`:

1. **Fotografia de perfil:**
   - ✅ `Fotografia de Ana Martins, a sorrir`
   - ❌ `foto`
2. **Imagem de um projeto:**
   - ✅ `Página inicial do site de receitas que fiz no curso`
   - ❌ `imagem` ou `captura1.png`
3. **Enfeite sem informação** (uma linha decorativa):
   - ✅ `alt=""` (vazio: o leitor de ecrã ignora-a)
   - ❌ não pôr `alt` nenhum

> 🧪 **Desafio rápido:** mudem o `src` para `imagens/fotoo.svg` (com um "o" a mais) e guardem. A imagem desaparece e aparece o ícone de imagem partida com o **texto do `alt`**. Voltem a pôr o nome certo.

> ⚠️ **Atenção:** o nome no `src` tem de ser **exatamente** igual ao do ficheiro, incluindo maiúsculas e extensão. `Foto.JPG` e `foto.jpg` podem funcionar no vosso computador e falhar no servidor. Mais uma razão para usar sempre minúsculas.

#### Passo 3: Abreviaturas (abbr e o Atributo title)

No parágrafo do curso, "HTML" é uma abreviatura. Vamos marcá-la:

```html
    <h3>Curso de Desenvolvimento Web</h3>
    <p>
      Desde 2026: <abbr title="HyperText Markup Language">HTML</abbr>, CSS,
      JavaScript e muito mais. <em>Ainda agora comecei!</em>
    </p>
```

- `<abbr>` marca uma **abreviatura**.
- O atributo global `title` dá uma **informação extra**, que aparece quando passam o rato por cima.

> 🧪 **Desafio rápido:** passem o rato por cima de "HTML" e esperem um segundo. Aparece "HyperText Markup Language".

> ⚠️ **Atenção:** o `title` só aparece com o rato: num telemóvel ninguém o vê. Nunca ponham **só** no `title` uma informação importante.

#### Passo 4: Mudar de Língua (span e o Atributo lang)

Em "Sobre mim", vamos dizer o que queremos ser: programadores **full-stack**, que fazem a parte do site que se vê (o *frontend*) e a parte que corre no servidor (o *backend*), como neste curso. "Full-stack" é uma expressão inglesa, e um leitor de ecrã configurado para português lê-a mal. Vamos avisá-lo. Mudem o segundo parágrafo de "Sobre mim":

```html
    <p>
      Em 2026 decidi mudar de vida e aprender a programar: quero ser
      programadora <span lang="en">full-stack</span>.
    </p>
```

- `<span>` é uma **caixa genérica**, sem significado nenhum: serve só para "agarrar" um bocado de texto e dar-lhe um atributo (e, mais tarde, um estilo com CSS).
- `lang="en"` diz que aquele bocado está em **inglês**. O leitor de ecrã muda a pronúncia.

Visualmente não muda nada, e está certo: há código que existe para quem **não vê** a página.

#### Passo 5: Citações e Caixas (blockquote e div)

Depois do percurso, acrescentem uma secção nova com o testemunho de alguém que trabalhou ou estudou convosco (um antigo chefe, um professor, um colega):

```html
    <!-- Testemunhos -->
    <h2>O que dizem de mim</h2>
    <div>
      <blockquote>
        <p>A Ana resolve qualquer problema com calma e com um sorriso.</p>
      </blockquote>
      <p>— Carla Sousa, gerente da loja onde a Ana trabalhou</p>
    </div>
```

> 💡 **Dica:** ainda não têm um testemunho? Escrevam um provisório e peçam esta semana uma frase verdadeira a alguém que vos conheça. Num portefólio real, só se publicam frases que a pessoa disse mesmo (e com autorização dela).

- `<blockquote>` é uma **citação longa**, de outra pessoa ou de outra fonte. O browser mostra-a com uma margem à esquerda. Lá dentro vai um parágrafo normal.
- `<div>` (*division*) é uma **caixa genérica de bloco**: junta a citação e o nome da autora num só grupo. Tal como o `span`, não tem significado; na aula 9 vamos usá-la para transformar este testemunho num "cartão" com fundo e borda.

**Bloco ou em linha?** Reparem na diferença:

1. **Elementos de bloco:** começam numa linha nova e ocupam a largura toda.
   - Exemplos: `h1`–`h6`, `p`, `div`, `blockquote`, `hr`.
2. **Elementos em linha** (*inline*): ficam dentro da linha de texto e ocupam só o necessário.
   - Exemplos: `strong`, `em`, `span`, `abbr`, `img`, `br`.

> 💡 **Dica:** `div` e `span` são as caixas "sem etiqueta". Usem-nas **só quando não existe** um elemento com significado para aquilo. Para uma citação existe `blockquote`; para texto importante existe `strong`. Na aula 4 vamos conhecer muitas mais caixas **com** significado.

> ✅ **Confirmem antes de avançar:**
>
> - A página mostra a vossa fotografia por cima do vosso nome.
> - Passar o rato por cima de "HTML" mostra "HyperText Markup Language".
> - O testemunho aparece com uma margem à esquerda.

---

### Parte 5: Boas Práticas e o Segundo Commit (Fechar a Aula) 📋

#### Passo 1: Boas Práticas de Escrita HTML

Uma lista de verificação que vamos usar até ao fim do curso:

- [ ] Tags e atributos em **minúsculas**; valores **entre aspas**.
- [ ] Código **indentado** (o Prettier ajuda).
- [ ] Um só **`h1`**; títulos sem saltar níveis.
- [ ] Todas as imagens têm **`alt`**.
- [ ] Primeiro procurem um **elemento com significado**; `div` e `span` só se não houver outro.
- [ ] Nomes de ficheiros e pastas em **minúsculas, sem espaços e sem acentos**.
- [ ] **Comentários** a marcar as zonas da página.
- [ ] O **validador do W3C** não mostra erros.

Validem agora o `index.html` no [validador do W3C](https://validator.w3.org/#validate_by_input).

#### Passo 2: Guardar no Git e Enviar para o GitHub

Vamos fazer o ciclo de trabalho:

```bash
git status
```

O Git mostra o `index.html` em *modified* (alterado) e a pasta `imagens/` em *untracked* (nova).

```bash
git add .
git commit -m "Adiciona fotografia, testemunho e abreviatura"
git push
```

Atualizem a página do GitHub: agora há **2 commits** e a pasta `imagens`. Cliquem no último commit para ver, a verde, as linhas acrescentadas hoje.

> ✅ **Confirmem antes de avançar:**
>
> - O `git log --oneline` mostra **dois** commits: `Adiciona fotografia, testemunho e abreviatura` e `Estrutura base da página inicial`.
> - O GitHub mostra a pasta `imagens` com a vossa fotografia.
> - O vosso `index.html` está igual ao código abaixo e o validador não mostra erros.

**O projeto no fim da aula** (o vosso, com os vossos dados em vez dos da Ana):

```
portefolio/                  ← agora é um repositório Git, também no GitHub
├── imagens/
│   └── foto.svg
└── index.html
```

```html
<!doctype html>
<html lang="pt-PT">
  <head>
    <meta charset="UTF-8" />
    <title>Ana Martins | Portefólio</title>
  </head>
  <body>
    <!-- Apresentação -->
    <img
      src="imagens/foto.svg"
      alt="Ilustração do rosto de Ana Martins, a sorrir"
      width="160"
      height="160"
    />
    <h1>Ana Martins</h1>
    <p>
      Futura <strong>programadora web</strong>, a aprender a construir sites de
      raiz.
    </p>

    <!-- Sobre mim -->
    <h2>Sobre mim</h2>
    <p>Sou de Setúbal e trabalhei dez anos no comércio, sempre ao balcão.</p>
    <p>
      Em 2026 decidi mudar de vida e aprender a programar: quero ser
      programadora <span lang="en">full-stack</span>.
    </p>

    <!-- Percurso -->
    <h2>O meu percurso</h2>

    <h3>Curso de Desenvolvimento Web</h3>
    <p>
      Desde 2026: <abbr title="HyperText Markup Language">HTML</abbr>, CSS,
      JavaScript e muito mais. <em>Ainda agora comecei!</em>
    </p>

    <h3>Comércio &amp; atendimento ao público</h3>
    <p>De 2016 a 2026. Aprendi a ouvir os clientes e a resolver problemas.</p>

    <!-- Testemunhos -->
    <h2>O que dizem de mim</h2>
    <div>
      <blockquote>
        <p>A Ana resolve qualquer problema com calma e com um sorriso.</p>
      </blockquote>
      <p>— Carla Sousa, gerente da loja onde a Ana trabalhou</p>
    </div>

    <!-- Contactos -->
    <h2>Contactos</h2>
    <p>
      E-mail: ana.martins@exemplo.pt<br />
      GitHub: ana-martins-dev
    </p>
    <p><strong>Disponível para estágio a partir de 2027.</strong></p>

    <!-- Rodapé (na aula 4 vamos usar a tag própria para isto) -->
    <hr />
    <p>&copy; 2026 Ana Martins</p>
  </body>
</html>
```

---

### 🆘 Se Algo Correr Mal

1. **Aparece `fatal: not a git repository`.**
   - Ainda não fizeram o `git init`, ou o terminal não está na pasta do projeto. Confirmem com `pwd` (Parte 2, Passo 1).
2. **Aparece `Author identity unknown` ou `Please tell me who you are` ao fazer o commit.**
   - Falta configurar o Git. Façam os dois comandos `git config` da Parte 2, Passo 2, e repitam o commit.
3. **Aparece `error: remote origin already exists`.**
   - Já correram o `git remote add` antes. Não faz mal: continuem para o comando seguinte.
4. **Aparece `error: src refspec main does not match any`.**
   - Ainda não têm nenhum commit. Voltem à Parte 2, Passos 4 e 5.
5. **Aparece `Authentication failed` ou `Permission denied`.**
   - A autenticação falhou. Corram outra vez `git push -u origin main` e iniciem sessão com a conta certa.
6. **O `git log` encheu o ecrã e não consigo escrever.**
   - Carreguem em **q** para sair.
7. **A imagem não aparece (só o ícone de imagem partida).**
   - O caminho no `src` não está igual ao ficheiro. Confirmem que a pasta se chama `imagens`, que o nome do ficheiro (por exemplo `foto.jpg` ou `foto.svg`) está igual no `src`, com as mesmas minúsculas e a mesma extensão, e que a pasta está ao lado do `index.html`.
8. **A pasta `imagens` não aparece no GitHub.**
   - Faltou o `git add .` antes do commit, ou faltou o `git push`. Corram `git status` para ver o que ficou por enviar.

---

### O Que Aprendemos Hoje ✅

Antes do exercício, confirmem que conseguem explicar por palavras vossas:

- [ ] O que é o controlo de versões e a diferença entre Git e GitHub.
- [ ] O que fazem `pwd` e `ls`.
- [ ] Para que serve `git config` e porque só se faz uma vez por computador.
- [ ] O que fazem `git init`, `git status`, `git add`, `git commit` e `git log`.
- [ ] O que é a área de preparação (a "caixa" da encomenda).
- [ ] O que é uma boa mensagem de commit.
- [ ] Como se liga um projeto ao GitHub e se envia com `git push`.
- [ ] As regras de escrita dos atributos.
- [ ] Para que servem o `src` e o `alt` de uma imagem, e o que é um bom `alt`.
- [ ] Para que servem `abbr`, `span`, `blockquote` e `div`.
- [ ] A diferença entre elementos de bloco e elementos em linha.

---

### 📖 Palavras Novas

- **Controlo de versões:** guardar a história de um projeto, com todas as versões e o que mudou em cada uma.
- **Git:** programa de controlo de versões que corre no vosso computador.
- **GitHub:** site que guarda cópias de repositórios Git na internet e permite partilhá-los.
- **Repositório (repo):** pasta de um projeto seguida pelo Git, com toda a sua história.
- **Commit:** um ponto de gravação do projeto: o estado dos ficheiros, com autor, data e mensagem.
- **Mensagem de commit:** frase curta que diz o que mudou num commit.
- **Hash:** código único que identifica um commit, como uma impressão digital.
- **Área de preparação (staging area):** onde ficam as alterações escolhidas com `git add`, à espera do próximo commit.
- **`git init`:** comando que transforma a pasta atual num repositório.
- **`git status`:** comando que mostra o que mudou e o que está preparado para o commit.
- **`git add`:** comando que coloca alterações na área de preparação.
- **`git commit`:** comando que cria um commit com o que está na área de preparação.
- **`git log`:** comando que mostra a história de commits.
- **Repositório remoto (remote):** cópia do repositório noutro sítio, por exemplo no GitHub. `origin` é o nome habitual.
- **Push:** enviar os commits do vosso computador para o repositório remoto.
- **Pull:** trazer para o vosso computador os commits que estão no repositório remoto.
- **Clone:** copiar um repositório remoto (com toda a história) para o vosso computador.
- **Branch (ramo):** versão paralela de um projeto; o ramo principal chama-se `main`.
- **`pwd` / `ls`:** comandos do terminal: "onde estou?" e "o que há nesta pasta?".
- **Atributo global:** atributo que pode ser usado em qualquer elemento, como `lang` ou `title`.
- **`src`:** atributo com o caminho do ficheiro a mostrar (por exemplo, de uma imagem).
- **Texto alternativo (`alt`):** descrição de uma imagem para quem não a consegue ver.
- **SVG:** formato de imagem desenhada com código; fica nítida em qualquer tamanho.
- **`abbr`:** elemento para abreviaturas; com `title`, mostra o significado.
- **`blockquote`:** elemento para citações longas de outra pessoa ou fonte.
- **`div`:** caixa genérica de bloco, sem significado.
- **`span`:** caixa genérica em linha, sem significado.
- **Elemento de bloco:** elemento que começa numa linha nova e ocupa a largura toda.
- **Elemento em linha (inline):** elemento que fica dentro da linha de texto.

### 🔗 Para Saber Mais

A maioria dos links abaixo está em inglês. Usem a tradução automática do browser (botão direito → **Traduzir para português**) se precisarem.

- [Livro oficial do Git (Pro Git), em português do Brasil](https://git-scm.com/book/pt-br/v2)
- [Imagens em HTML (MDN)](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/HTML_images)
- [Como escrever um bom texto alternativo (W3C)](https://www.w3.org/WAI/tutorials/images/decision-tree/)

---

# Exercício Final: Ovos Moles de Aveiro 🥚

Agora é a vossa vez, sozinhos. O enunciado também está na ficha [`ex-003.md`](../../exercicios/ex-003.md). Os ficheiros de que precisam estão na pasta [`exercicios/ex-003/`](../../exercicios/ex-003/).

### Missão 1: Os Exercícios Também no GitHub

1. No VS Code, abram a pasta `exercicios-uf1.1` (**File** → **Open Folder...**) e abram um terminal. Confirmem com `pwd` que estão nessa pasta.
2. Criem o repositório (`git init`), adicionem tudo e façam um commit com a mensagem `Exercícios das aulas 1 e 2`.
3. No GitHub, criem um repositório **vazio** e **público** chamado `exercicios-uf1.1`.
4. Liguem-no e enviem (os três comandos da Parte 3, Passo 2).
5. Confirmem no GitHub que aparecem as pastas `sessao-01` e `sessao-02`.

> ⚠️ **Atenção:** o Git **não guarda pastas vazias**. A pasta `sessao-03` só vai aparecer no GitHub quando tiver lá dentro pelo menos um ficheiro.

> ⚠️ **Atenção:** cada projeto tem o **seu** repositório. Nunca façam `git init` na pasta `dawfs`, que contém os dois.

### Missão 2: A Minha Cidade, Versão 3

1. Criem a pasta `sessao-03` e copiem para lá o `cidade.html` da aula 2.
2. Dentro de `sessao-03`, criem a pasta `imagens` e ponham lá o ficheiro [`cidade.svg`](../../exercicios/ex-003/imagens/cidade.svg) (ou uma fotografia vossa da cidade, com um nome sem espaços nem acentos, por exemplo `centro.jpg`).
3. Antes do `h1`, insiram a imagem com `src`, um bom `alt`, `width="240"` e `height="160"`.
4. Usem um `<abbr title="...">` numa abreviatura (por exemplo, *UNESCO* ou *CP*) e um `<span lang="...">` numa palavra ou nome noutra língua (por exemplo, o nome romano da cidade, em latim: `lang="la"`).
5. Acrescentem uma secção **Um ditado sobre a minha terra** com um ditado ou uma frase sobre a cidade (`blockquote`) e o autor (ou "Ditado popular"), os dois dentro de uma `div`.
6. Façam o ciclo de trabalho: `git add .`, `git commit -m "Página da cidade versão 3"`, `git push`.

### Missão 3: A Página dos Ovos Moles

1. Copiem para a pasta `sessao-03` o ficheiro [`ovos-moles.txt`](../../exercicios/ex-003/ovos-moles.txt) e, para a pasta `sessao-03/imagens`, a imagem [`ovos-moles.svg`](../../exercicios/ex-003/imagens/ovos-moles.svg).
2. Criem o ficheiro `ovos-moles.html` com a estrutura completa e passem para lá o texto, escolhendo o elemento certo para cada parte (título principal, capítulos, parágrafos).
3. No sítio indicado por `[imagem: ...]`, insiram a imagem com um **bom `alt`** (usem a descrição que lá está), `width="240"` e `height="200"`.
4. Marquem a abreviatura **IGP** com `<abbr>` e o significado no `title`.
5. A citação da Dona Rosa vai num `blockquote`; o nome dela num parágrafo a seguir; os dois dentro de uma `div`.
6. Usem pelo menos um `<strong>` e um `<em>`, um comentário antes de cada capítulo e um rodapé com `<hr />` e `&copy;`.
7. Validem a página no validador do W3C.
8. Façam o ciclo de trabalho, com a mensagem `Página dos ovos moles`.

**Critérios de sucesso:**

- [ ] A página tem a estrutura completa; o separador mostra "Ovos Moles de Aveiro".
- [ ] A imagem aparece e tem um `alt` que a descreve.
- [ ] Passar o rato por cima de "IGP" mostra "Indicação Geográfica Protegida".
- [ ] A citação está num `blockquote` e, com o nome da autora, dentro de uma `div`.
- [ ] O validador não mostra erros.
- [ ] O GitHub mostra a página e a imagem, e o `git log --oneline` mostra o commit `Página dos ovos moles`.

### Missão 4: O Relatório

Entreguem as respostas:

1. Os repositórios:
   Quais são os endereços dos vossos dois repositórios no GitHub (`portefolio` e `exercicios-uf1.1`)?
   Resposta: [Preencher]

2. O ciclo de trabalho:
   Expliquem, por palavras vossas, o que fazem `git add`, `git commit` e `git push`, e porque é que são três passos separados.
   Resposta: [Preencher]

3. O texto alternativo:
   Que `alt` escreveram para a imagem dos ovos moles? Quem vai precisar desse texto?
   Resposta: [Preencher]

---

### 🚀 Desafio Bónus (Para os mais rápidos)

1. Mudem o `alt` da imagem dos ovos moles, façam um novo commit e enviem-no. No GitHub, abram esse commit: conseguem ver a linha antiga (a vermelho) e a nova (a verde)?
2. Corram `git log --oneline` no repositório `exercicios-uf1.1`. Escolham a mensagem de commit menos clara e escrevam, no relatório, como a melhorariam.
