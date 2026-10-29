# Exercício Prático: O Festival da Sardinha 🐟

Hoje organizámos o portefólio com elementos semânticos: `header`, `nav`, `main`, `section`, `article`, `aside` e `footer`. Agora é a vossa vez: vão reorganizar a página da vossa cidade e construir sozinhos uma página sobre um festival gastronómico, usando a estrutura semântica desde o início.

O vosso objetivo é repetir sozinhos a organização com elementos semânticos e perceber quando usar cada um.

Os ficheiros de que precisam estão na pasta [`ex-004/`](./ex-004/): `festival-sardinha.txt`.

### Missão 1: A Minha Cidade, Versão 4

1. Criem a pasta `sessao-04` dentro de `exercicios-uf1.1` e copiem para lá **todo o conteúdo** da pasta `sessao-03` (incluindo a pasta `imagens`).
2. Abram o `cidade.html` e organizem a página com elementos semânticos:
   - Envolvam o título (`h1`) e a imagem num `header`.
   - Envolvam todo o conteúdo entre o `header` e o rodapé num `main`.
   - Cada zona com `h2` passa a ser uma `section`.
   - O ditado (que está num `blockquote` dentro de uma `div`) passa a ser um `article` (em vez da `div`).
   - Substituam o `<hr />` e o parágrafo do `©` por um `footer`.
3. Validem no [validador do W3C](https://validator.w3.org/#validate_by_input).
4. Façam o ciclo de trabalho:
   - `git add .`
   - `git commit -m "Cidade com elementos semânticos"`
   - `git push`

### Missão 2: A Página do Festival da Sardinha

Vão construir uma página sobre um festival gastronómico, do zero e já com a estrutura semântica certa.

1. Copiem para a pasta `sessao-04` o ficheiro [`festival-sardinha.txt`](./ex-004/festival-sardinha.txt).
2. Criem o ficheiro `festival-sardinha.html` com a estrutura HTML completa (`<!doctype html>`, `<html lang="pt-PT">`, `head`, `body`). O título do separador deve ser "Festival da Sardinha — Portimão".
3. Organizem o conteúdo com os elementos semânticos certos:
   - `header` com o título do festival (`h1`) e a frase de abertura (`p`).
   - `nav` com o texto: `Programa · Gastronomia · Testemunho · Informações`.
   - `main` com todo o conteúdo.
   - Uma `section` para cada capítulo (Programa, Gastronomia, Informações práticas), cada uma com o seu título (`h2`).
   - A secção do testemunho deve conter um `article` com a citação em `blockquote` e o nome do autor num parágrafo.
   - A curiosidade sobre a sardinha vai num `aside`, dentro do `main`.
   - `footer` com `&copy; 2026 Festival da Sardinha — Portimão`.
4. Usem pelo menos um `strong`, um `em` e um comentário HTML antes de cada secção.
5. Validem no [validador do W3C](https://validator.w3.org/#validate_by_input).
6. Façam o ciclo de trabalho, com a mensagem `Página do festival da sardinha`.

**Critérios de sucesso:**

- [ ] A página tem `header`, `nav`, `main`, `section` (pelo menos 3), `article`, `aside` e `footer`.
- [ ] Só há um `main`.
- [ ] Cada `section` tem um título (`h2`).
- [ ] O testemunho está num `article`, com `blockquote`.
- [ ] A curiosidade está num `aside`.
- [ ] O validador não mostra erros.
- [ ] O GitHub mostra a página e o `git log --oneline` mostra o commit `Página do festival da sardinha`.

A vossa pasta `exercicios-uf1.1` deve ficar assim:

```
exercicios-uf1.1/            ← repositório Git, também no GitHub
├── sessao-01/
├── sessao-02/
├── sessao-03/
│   ├── imagens/
│   ├── cidade.html
│   ├── ovos-moles.html
│   └── ovos-moles.txt
└── sessao-04/
    ├── imagens/
    │   ├── cidade.svg
    │   └── ovos-moles.svg
    ├── cidade.html
    ├── ovos-moles.html
    ├── ovos-moles.txt
    └── festival-sardinha.html
```

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
