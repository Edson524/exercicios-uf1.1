# Guia Prático - UF 1.1 (Aula 4)

## Estruturação de Páginas: Dar Significado às Zonas do Site 🏗️

- **Objetivo:** Aprender a organizar uma página HTML com os elementos semânticos `header`, `nav`, `main`, `section`, `article`, `aside` e `footer`, transformando o portefólio numa página bem estruturada que qualquer browser, leitor de ecrã ou motor de busca percebe.

> 📖 **Como estudar com este guia:** este guia tem os mesmos passos que fizemos na aula, pela mesma ordem. Sigam as Partes e os Passos **por ordem**, no vosso computador, e escrevam o código e os comandos **à mão** (não copiem e colem). No fim de cada etapa há uma caixa **✅ Confirmem antes de avançar**: só passem à frente quando o vosso resultado for igual ao que lá está. Se algo não funcionar, vejam a secção **🆘 Se Algo Correr Mal**, no fim do guia.

> 💡 **Mac:** sempre que aparecer a tecla **Ctrl**, usem a tecla **Cmd (⌘)**.

> 🔙 **Ponto de partida:** a pasta `portefolio` com o `index.html` da aula 3 (se faltaram, copiem a pasta [`projeto/sessao-03/`](../../projeto/sessao-03/)). O projeto já deve estar no GitHub.

---

### Parte 1: Porquê Elementos Semânticos? (As Placas da Estrada) 🪧

#### Passo 1: Abrir o Projeto e Rever

1. Abram a pasta `portefolio` no VS Code (**File** → **Open Folder...**).
2. Abram o `index.html` com o **Live Server**.
3. Olhem para a página: tem fotografia, nome, secções, testemunho e rodapé. Mas se olharem para o código, é tudo `h1`, `h2`, `p`, `div`... O browser mostra bem, mas **não sabe** o que é o cabeçalho, o que é o conteúdo principal e o que é o rodapé.

#### Passo 2: O Problema das Caixas Sem Nome

Imaginem um supermercado sem placas nos corredores. Os produtos estão lá, mas ninguém sabe onde encontrar o que precisa. As `div` são como **caixas sem etiqueta**: servem para agrupar, mas não dizem o que está lá dentro.

O HTML5 trouxe **elementos semânticos**: caixas que já vêm **com nome**. Não mudam o aspeto da página (isso é trabalho do CSS), mas dizem ao browser, ao Google e aos leitores de ecrã **o que cada zona significa**.

#### Passo 3: Os Elementos Semânticos de Estrutura

Pensem numa página como uma **casa**:

```
┌─────────────────────────────────────────────┐
│  header   (o letreiro da loja)              │
│  ┌──────────────────────────────────────┐   │
│  │  nav   (o mapa / menu de navegação)  │   │
│  └──────────────────────────────────────┘   │
├─────────────────────────────────────────────┤
│  main   (a sala principal)                  │
│  ┌──────────────────────────────────────┐   │
│  │  section   (uma sala temática)       │   │
│  │  ┌──────────────────────────────┐    │   │
│  │  │  article   (um quadro / peça) │   │   │
│  │  └──────────────────────────────┘    │   │
│  └──────────────────────────────────────┘   │
│  ┌──────────────────────────────────────┐   │
│  │  aside   (a nota de rodapé lateral)  │   │
│  └──────────────────────────────────────┘   │
├─────────────────────────────────────────────┤
│  footer   (a placa de informação à saída)   │
└─────────────────────────────────────────────┘
```

Cada elemento, em detalhe:

| Elemento    | Para que serve | Analogia |
|-------------|---------------|----------|
| `header`    | Cabeçalho da página ou de uma secção: o nome, o logótipo, o menu. | O letreiro da loja. |
| `nav`       | Grupo de links de navegação (o menu). | O mapa do centro comercial. |
| `main`      | O conteúdo principal da página. **Só pode haver um por página.** | A sala principal da casa. |
| `section`   | Uma parte temática do conteúdo, normalmente com um título. | Uma sala temática no museu. |
| `article`   | Um conteúdo independente, que faz sentido sozinho (um post, uma notícia, um testemunho). | Um quadro que se pode levar para outra exposição. |
| `aside`     | Conteúdo secundário, relacionado mas não essencial (uma nota, uma curiosidade). | A nota lateral num livro. |
| `footer`    | Rodapé da página ou de uma secção: direitos de autor, links úteis. | A placa de informação à saída. |

> 💡 **Dica:** estes elementos são todos **caixas de bloco**, como a `div`. A diferença é o **significado**: em vez de uma caixa sem nome, dizem "isto é o cabeçalho", "isto é o conteúdo principal", etc.

> ✅ **Confirmem antes de avançar:** conseguem apontar, no vosso portefólio, o que devia ser o cabeçalho, o conteúdo principal e o rodapé? Pensem nisso antes de continuar.

---

### Parte 2: O Cabeçalho e o Rodapé (header e footer) 🏷️

#### Passo 1: Envolver o Cabeçalho com header

Abram o `index.html`. A zona do cabeçalho é a apresentação: a fotografia, o nome e a frase. Vamos envolvê-la num `header`:

```html
<header>
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
</header>
```

Guardem e olhem para a página. **Não mudou nada** visualmente, e está certo! O `header` não tem estilo próprio: é uma caixa transparente que diz "isto é o cabeçalho".

> 💡 **Dica:** o `header` **não** é o `head`. O `head` é a parte invisível do documento (título, charset); o `header` é a parte visível, normalmente o topo da página com o nome e o menu.

#### Passo 2: Substituir o Rodapé com footer

No fim da página, temos um `<hr />` e um parágrafo com `©`. Substituam o comentário `<!-- Rodapé -->`, o `<hr />` e o parágrafo por um `footer`:

**Antes:**

```html
<!-- Rodapé (na aula 4 vamos usar a tag própria para isto) -->
<hr />
<p>&copy; 2026 Ana Martins</p>
```

**Depois:**

```html
<footer>
  <p>&copy; 2026 Ana Martins</p>
</footer>
```

O `<hr />` já não faz falta: o `footer` marca bem a separação. Mais tarde, com CSS, vamos dar-lhe um fundo e uma margem que o destaquem.

> ✅ **Confirmem antes de avançar:** a página continua a funcionar exatamente como antes. No código, a fotografia e o nome estão dentro de `<header>` e o `© 2026` está dentro de `<footer>`. O `<hr />` do rodapé já não está lá.

---

### Parte 3: O Conteúdo Principal e as Secções (main e section) 📦

#### Passo 1: Envolver Tudo com main

Tudo o que está **entre** o `header` e o `footer` é o conteúdo principal. Envolvam-no com `main`:

```html
<header>
  ...
</header>

<main>
  <!-- Sobre mim -->
  <h2>Sobre mim</h2>
  ...

  <!-- Percurso -->
  <h2>O meu percurso</h2>
  ...

  <!-- Testemunhos -->
  <h2>O que dizem de mim</h2>
  ...

  <!-- Contactos -->
  <h2>Contactos</h2>
  ...
</main>

<footer>
  ...
</footer>
```

> ⚠️ **Atenção:** só pode haver **um** `main` por página. É a regra: o conteúdo principal é um só.

#### Passo 2: Dividir em Secções com section

Dentro do `main`, cada zona com o seu `h2` é uma secção. Envolvam cada uma com `section`:

```html
<main>
  <section>
    <!-- Sobre mim -->
    <h2>Sobre mim</h2>
    <p>Sou de Setúbal e trabalhei dez anos no comércio, sempre ao balcão.</p>
    <p>
      Em 2026 decidi mudar de vida e aprender a programar: quero ser
      programadora <span lang="en">full-stack</span>.
    </p>
  </section>

  <section>
    <!-- Percurso -->
    <h2>O meu percurso</h2>

    <h3>Curso de Desenvolvimento Web</h3>
    <p>
      Desde 2026: <abbr title="HyperText Markup Language">HTML</abbr>, CSS,
      JavaScript e muito mais. <em>Ainda agora comecei!</em>
    </p>

    <h3>Comércio &amp; atendimento ao público</h3>
    <p>De 2016 a 2026. Aprendi a ouvir os clientes e a resolver problemas.</p>
  </section>

  <section>
    <!-- Testemunhos -->
    <h2>O que dizem de mim</h2>
    <div>
      <blockquote>
        <p>A Ana resolve qualquer problema com calma e com um sorriso.</p>
      </blockquote>
      <p>— Carla Sousa, gerente da loja onde a Ana trabalhou</p>
    </div>
  </section>

  <section>
    <!-- Contactos -->
    <h2>Contactos</h2>
    <p>
      E-mail: ana.martins@exemplo.pt<br />
      GitHub: ana-martins-dev
    </p>
    <p><strong>Disponível para estágio a partir de 2027.</strong></p>
  </section>
</main>
```

> 💡 **Dica:** não precisam de pôr `section` em tudo. A regra é: usem `section` quando a zona tem um **título** (`h2`, `h3`...) e faz sentido como **parte temática** do conteúdo. Se só querem agrupar para dar estilo, usem `div`.

> ✅ **Confirmem antes de avançar:** a página continua igual. No código, dentro de `main` há quatro `section`, cada uma com o seu `h2`.

---

### Parte 4: O Testemunho como article e uma Nota Lateral (article e aside) 📰

#### Passo 1: Transformar o Testemunho em article

O testemunho faz sentido **sozinho**: poderíamos pô-lo noutro site e continuaria a perceber-se. Isso faz dele um `article`. Dentro da secção de testemunhos, substituam a `div` por um `article`:

**Antes:**

```html
<div>
  <blockquote>
    <p>A Ana resolve qualquer problema com calma e com um sorriso.</p>
  </blockquote>
  <p>— Carla Sousa, gerente da loja onde a Ana trabalhou</p>
</div>
```

**Depois:**

```html
<article>
  <blockquote>
    <p>A Ana resolve qualquer problema com calma e com um sorriso.</p>
  </blockquote>
  <p>— Carla Sousa, gerente da loja onde a Ana trabalhou</p>
</article>
```

A diferença visual é zero, mas o significado é grande: o browser e os leitores de ecrã sabem agora que aquilo é **um conteúdo independente**.

#### Passo 2: Quando é article, quando é section?

A regra de ouro:

- **`article`:** faz sentido sozinho, fora da página. Exemplos: um post de blog, um comentário, um testemunho, uma notícia, um produto.
- **`section`:** é uma parte temática de algo maior. Exemplos: "Sobre mim", "O meu percurso", "Contactos".

Na dúvida, perguntem: "posso copiar isto para outro site e percebe-se sem o resto?". Se sim, é `article`. Se não, é `section`.

#### Passo 3: Acrescentar uma Nota Lateral com aside

No "Sobre mim", vamos acrescentar uma curiosidade que não é essencial ao conteúdo. Dentro da secção "Sobre mim", a seguir ao último parágrafo:

```html
<aside>
  <p>
    💡 <strong>Sabiam que…</strong> o primeiro site da história foi publicado em
    1991, no CERN, por Tim Berners-Lee.
  </p>
</aside>
```

O `aside` diz: "isto está relacionado com o conteúdo à volta, mas não é essencial; se o tirarmos, o texto principal continua a fazer sentido". É perfeito para curiosidades, notas laterais e "caixas de dica".

> ✅ **Confirmem antes de avançar:**
>
> - O testemunho está dentro de um `article`, não de uma `div`.
> - A curiosidade sobre o primeiro site está dentro de um `aside`, na secção "Sobre mim".
> - A página continua a funcionar e a mostrar tudo corretamente.

---

### Parte 5: O Menu de Navegação (nav) 🧭

#### Passo 1: Criar um Menu Simples

Por agora temos só uma página, mas vamos preparar o menu que, na próxima aula, vai ligar a várias páginas. Dentro do `header`, a seguir à frase de apresentação, acrescentem:

```html
<nav>
  <p>Início · Sobre · Percurso · Contactos</p>
</nav>
```

> 💡 **Dica:** na próxima aula vamos transformar estes textos em **links** (`<a>`) que saltam para cada secção ou para outra página. Por agora, o importante é marcar a zona como `nav`.

O `nav` diz ao browser e aos leitores de ecrã: "aqui está a navegação do site". Um leitor de ecrã pode anunciar "navegação" e permitir saltar diretamente para os links. Uma página pode ter mais do que um `nav` (por exemplo, um no cabeçalho e outro no rodapé), mas a maioria tem só um.

#### Passo 2: Rever a Estrutura Completa

Olhem para o vosso código. A estrutura agora é:

```
<html>
  <head> ... </head>
  <body>
    <header>
      foto, nome, frase, nav
    </header>
    <main>
      <section> Sobre mim + aside </section>
      <section> Percurso </section>
      <section> Testemunhos + article </section>
      <section> Contactos </section>
    </main>
    <footer>
      copyright
    </footer>
  </body>
</html>
```

Comparem com a estrutura da aula passada: o conteúdo é o mesmo, mas agora cada zona tem **um nome que diz o que é**. É como pôr placas nos corredores do supermercado.

> ✅ **Confirmem antes de avançar:** a página mostra exatamente o mesmo que antes. Se inspecionarem com as DevTools (botão direito → **Inspecionar**), veem os elementos `header`, `nav`, `main`, `section`, `article`, `aside` e `footer`.

---

### Parte 6: div vs. Elementos Semânticos (Quando Usar Cada Um) 🤔

#### Passo 1: A Regra de Ouro

Já sabem esta dica da aula 3: **primeiro procurem um elemento com significado**. Se não existir, usem `div` ou `span`.

Vamos rever com exemplos do nosso portefólio:

| Situação | Elemento certo | Porquê |
|----------|----------------|--------|
| O topo da página com nome e menu | `header` | É o cabeçalho. |
| O menu com links | `nav` | É navegação. |
| Todo o conteúdo principal | `main` | É o conteúdo principal (só um). |
| "Sobre mim" ou "Contactos" | `section` | São partes temáticas com título. |
| O testemunho | `article` | Faz sentido sozinho. |
| Uma curiosidade | `aside` | Conteúdo secundário. |
| O `© 2026` | `footer` | É o rodapé. |
| Um grupo de elementos que só precisa de estilo CSS | `div` | Não tem significado, só agrupa. |
| Um bocado de texto que só precisa de estilo CSS | `span` | Não tem significado, só marca texto. |

#### Passo 2: Porquê Fazer Isto?

Três razões:

1. **Acessibilidade.** Os leitores de ecrã usam estes elementos para criar um **mapa da página**. Com `header`, `nav`, `main` e `footer`, uma pessoa cega pode saltar diretamente para o conteúdo principal, sem ouvir o menu todo outra vez.

2. **SEO (motores de busca).** O Google percebe melhor a página quando o conteúdo principal está num `main`, os títulos fazem sentido e a navegação está num `nav`.

3. **Manutenção.** Para vós e para qualquer programador que leia o vosso código: `<section>` diz mais do que `<div>`, sem precisar de ler o que está lá dentro.

> 💡 **Dica:** se alguma vez hesitarem entre `section` e `div`, perguntem: "esta zona tem um título e é uma parte temática do conteúdo?". Se sim, `section`. Se é só para agrupar e dar estilo, `div`.

---

### Parte 7: Boas Práticas e o Commit (Fechar a Aula) 📋

#### Passo 1: Lista de Verificação

- [ ] A página tem `header`, `main` e `footer`.
- [ ] Só há **um** `main`.
- [ ] Cada zona temática com título está numa `section`.
- [ ] O testemunho está num `article`.
- [ ] O menu está num `nav`.
- [ ] O `aside` contém conteúdo secundário, não essencial.
- [ ] O validador do W3C não mostra erros.
- [ ] O código está indentado (o Prettier arruma).

Validem agora o `index.html` no [validador do W3C](https://validator.w3.org/#validate_by_input).

#### Passo 2: Guardar no Git e Enviar para o GitHub

```bash
git status
git add .
git commit -m "Organiza a página com elementos semânticos"
git push
```

> ✅ **Confirmem antes de avançar:**
>
> - O `git log --oneline` mostra o novo commit: `Organiza a página com elementos semânticos`.
> - O GitHub mostra o `index.html` atualizado.
> - O vosso `index.html` está igual ao código abaixo e o validador não mostra erros.

**O projeto no fim da aula** (o vosso, com os vossos dados em vez dos da Ana):

```
portefolio/
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
    <header>
      <!-- Apresentação -->
      <img
        src="imagens/foto.svg"
        alt="Ilustração do rosto de Ana Martins, a sorrir"
        width="160"
        height="160"
      />
      <h1>Ana Martins</h1>
      <p>
        Futura <strong>programadora web</strong>, a aprender a construir sites
        de raiz.
      </p>
      <nav>
        <p>Início · Sobre · Percurso · Contactos</p>
      </nav>
    </header>

    <main>
      <section>
        <!-- Sobre mim -->
        <h2>Sobre mim</h2>
        <p>
          Sou de Setúbal e trabalhei dez anos no comércio, sempre ao balcão.
        </p>
        <p>
          Em 2026 decidi mudar de vida e aprender a programar: quero ser
          programadora <span lang="en">full-stack</span>.
        </p>
        <aside>
          <p>
            💡 <strong>Sabiam que…</strong> o primeiro site da história foi
            publicado em 1991, no CERN, por Tim Berners-Lee.
          </p>
        </aside>
      </section>

      <section>
        <!-- Percurso -->
        <h2>O meu percurso</h2>

        <h3>Curso de Desenvolvimento Web</h3>
        <p>
          Desde 2026: <abbr title="HyperText Markup Language">HTML</abbr>, CSS,
          JavaScript e muito mais. <em>Ainda agora comecei!</em>
        </p>

        <h3>Comércio &amp; atendimento ao público</h3>
        <p>
          De 2016 a 2026. Aprendi a ouvir os clientes e a resolver problemas.
        </p>
      </section>

      <section>
        <!-- Testemunhos -->
        <h2>O que dizem de mim</h2>
        <article>
          <blockquote>
            <p>
              A Ana resolve qualquer problema com calma e com um sorriso.
            </p>
          </blockquote>
          <p>— Carla Sousa, gerente da loja onde a Ana trabalhou</p>
        </article>
      </section>

      <section>
        <!-- Contactos -->
        <h2>Contactos</h2>
        <p>
          E-mail: ana.martins@exemplo.pt<br />
          GitHub: ana-martins-dev
        </p>
        <p>
          <strong>Disponível para estágio a partir de 2027.</strong>
        </p>
      </section>
    </main>

    <footer>
      <p>&copy; 2026 Ana Martins</p>
    </footer>
  </body>
</html>
```

---

### 🆘 Se Algo Correr Mal

1. **O validador diz `Element "main" not allowed as child of element "..."`.** 
   - O `main` tem de estar **diretamente dentro** do `body`, não dentro de outra `section` ou `div`. Confirmem a indentação.
2. **O validador diz `Element "header" not allowed here`.** 
   - Certifiquem-se de que o `header` está diretamente dentro do `body` (cabeçalho da página) ou dentro de um `article` ou `section` (cabeçalho dessa secção), nunca dentro de outro `header` ou `footer`.
3. **O validador diz `Section lacks heading`.** 
   - É um aviso, não um erro. Significa que uma `section` não tem título (`h2`, `h3`...). Se a secção não tem título, talvez devesse ser uma `div`.
4. **A página mudou de aspeto depois de acrescentar os elementos semânticos.**
   - Não devia mudar. Confirmem que não apagaram nenhum conteúdo ao envolver com as novas tags. Comparem com o código da aula 3 e com o código final desta aula.
5. **Não sei se é `section` ou `div`.**
   - Perguntem: "esta zona tem um título e é uma parte temática?". Se sim, `section`. Se só precisa de agrupar para estilo, `div`.
6. **Não sei se é `article` ou `section`.**
   - Perguntem: "isto faz sentido sozinho, fora desta página?". Se sim, `article`. Se é uma parte de algo maior, `section`.

---

### O Que Aprendemos Hoje ✅

Antes do exercício, confirmem que conseguem explicar por palavras vossas:

- [ ] Para que servem os elementos semânticos e porque são melhores do que `div` para tudo.
- [ ] O que é o `header` e como é diferente do `head`.
- [ ] Para que serve o `nav`.
- [ ] Porque só pode haver um `main` por página.
- [ ] O que é uma `section` e quando a usar.
- [ ] O que é um `article` e a diferença para `section`.
- [ ] Para que serve o `aside`.
- [ ] O que é o `footer`.
- [ ] A regra: procurar primeiro um elemento com significado; `div`/`span` só quando não há outro.
- [ ] Três razões para usar elementos semânticos (acessibilidade, SEO, manutenção).

---

### 📖 Palavras Novas

- **Elemento semântico:** elemento HTML que descreve o **significado** do seu conteúdo, não apenas o aspeto.
- **`header`:** cabeçalho da página ou de uma secção (nome, logótipo, menu).
- **`nav`:** grupo de links de navegação.
- **`main`:** conteúdo principal da página; só pode haver um por página.
- **`section`:** parte temática do conteúdo, normalmente com um título.
- **`article`:** conteúdo independente, que faz sentido sozinho fora da página.
- **`aside`:** conteúdo secundário, relacionado mas não essencial.
- **`footer`:** rodapé da página ou de uma secção (direitos de autor, links úteis).
- **Acessibilidade:** fazer com que um site funcione para toda a gente, incluindo pessoas com deficiências (visuais, motoras, cognitivas).
- **SEO (Search Engine Optimization):** conjunto de técnicas para que os motores de busca (como o Google) encontrem e mostrem o site.
- **Leitor de ecrã (screen reader):** programa que lê o conteúdo de um site em voz alta, usado por pessoas cegas ou com dificuldades visuais.

### 🔗 Para Saber Mais

A maioria dos links abaixo está em inglês. Usem a tradução automática do browser (botão direito → **Traduzir para português**) se precisarem.

- [Elementos semânticos do HTML (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Semantics#semantics_in_html)
- [Estrutura de documentos e secções (MDN)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#content_sectioning)
- [Usar ARIA landmarks para identificar regiões da página (W3C)](https://www.w3.org/WAI/tutorials/page-structure/regions/)
- [HTML semântico: o que é e porquê (web.dev)](https://web.dev/learn/html/semantic-html)

---

# Exercício Final: O Festival da Sardinha 🐟

Agora é a vossa vez, sozinhos. O enunciado também está na ficha [`ex-004.md`](../../exercicios/ex-004.md). Os ficheiros de que precisam estão na pasta [`exercicios/ex-004/`](../../exercicios/ex-004/).

### Missão 1: A Minha Cidade, Versão 4

1. Criem a pasta `sessao-04` dentro de `exercicios-uf1.1` e copiem para lá **todo o conteúdo** da pasta `sessao-03` (incluindo a pasta `imagens`).
2. Abram o `cidade.html` e organizem a página com elementos semânticos:
   - Envolvam o título (`h1`) e a imagem num `header`.
   - Envolvam todo o conteúdo entre o `header` e o rodapé num `main`.
   - Cada zona com `h2` passa a ser uma `section`.
   - O ditado (que está num `blockquote` dentro de uma `div`) passa a ser um `article` (em vez da `div`).
   - Substituam o `<hr />` e o parágrafo do `©` por um `footer`.
3. Validem no [validador do W3C](https://validator.w3.org/#validate_by_input).
4. Façam o ciclo de trabalho: `git add .`, `git commit -m "Cidade com elementos semânticos"`, `git push`.

### Missão 2: A Página do Festival da Sardinha

Vão construir uma página sobre um festival gastronómico, do zero e já com a estrutura semântica certa.

1. Copiem para a pasta `sessao-04` o ficheiro [`festival-sardinha.txt`](../../exercicios/ex-004/festival-sardinha.txt).
2. Criem o ficheiro `festival-sardinha.html` com a estrutura HTML completa (`<!doctype html>`, `<html lang="pt-PT">`, `head`, `body`).
3. Organizem o conteúdo com os elementos semânticos certos:
   - `header` com o título do festival e uma frase de abertura.
   - `nav` com o texto: `Programa · Gastronomia · Testemunho · Informações`.
   - `main` com todo o conteúdo.
   - Uma `section` para cada capítulo (Programa, Gastronomia, Informações práticas).
   - Um `article` para o testemunho do visitante (a citação em `blockquote` e o nome do autor).
   - Um `aside` com a curiosidade sobre a sardinha.
   - `footer` com `&copy;`.
4. Usem pelo menos um `strong`, um `em` e um comentário HTML.
5. Validem no validador do W3C.
6. Façam o ciclo de trabalho, com a mensagem `Página do festival da sardinha`.

**Critérios de sucesso:**

- [ ] A página tem `header`, `nav`, `main`, `section`, `article`, `aside` e `footer`.
- [ ] Só há um `main`.
- [ ] Cada `section` tem um título.
- [ ] O testemunho está num `article`.
- [ ] A curiosidade está num `aside`.
- [ ] O validador não mostra erros.
- [ ] O GitHub mostra a página e o `git log --oneline` mostra o commit.

### Missão 3: O Relatório

Entreguem as respostas:

1. A diferença:
   Expliquem a diferença entre `header` e `head`, por palavras vossas.
   Resposta: [Preencher]

2. article ou section?
   Imaginem um blog com vários posts. Cada post é um `article` ou uma `section`? E as partes dentro de cada post (introdução, corpo, conclusão)?
   Resposta: [Preencher]

3. Porquê semântica?
   Deem dois exemplos concretos de quem beneficia quando usamos elementos semânticos em vez de `div` para tudo.
   Resposta: [Preencher]

---

### 🚀 Desafio Bónus (Para os mais rápidos)

1. Na página do festival, acrescentem um **segundo testemunho** dentro da mesma secção, cada um no seu `article`. Os dois devem aparecer um a seguir ao outro.
2. Abram o vosso portefólio nas **DevTools** (botão direito → **Inspecionar**) e usem a árvore de acessibilidade (**Accessibility** no painel) para ver como o browser organiza os _landmarks_ da página. Quantos encontram?
