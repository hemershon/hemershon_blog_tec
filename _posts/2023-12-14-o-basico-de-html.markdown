---
title: "O básico de HTML"
categories:
  - web
  - HTML
  - CSS
  - iniciante
tags:
  - web
  - html
  - css
---
Vou explicar a base do HTML de forma didática!

HTML, que significa **H**yper**t**ext **M**arkup **L**anguage (Linguagem de Marcação de Hipertexto), é a linguagem de marcação padrão para a criação de páginas web. Vamos quebrar isso em partes:

1. **Hipertexto:** Isso significa que você pode clicar em texto, imagens ou links para ir para outras páginas ou recursos relacionados. É a essência da navegação na web.

2. **Linguagem de Marcação:** O HTML usa "marcadores" ou "tags" para envolver diferentes partes do seu conteúdo e dar significado a eles. Essas tags são interpretadas pelos navegadores web para exibir o conteúdo da página.

Aqui está um exemplo simples:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Minha Primeira Página</title>
</head>
<body>

    <h1>Olá, Mundo!</h1>
    <p>Esta é a minha primeira página web.</p>

</body>
</html>
```

Agora, uma breve explicação das partes:

- `<!DOCTYPE html>`: Indica ao navegador que o documento está usando a versão mais recente do HTML.

- `<html>`: É o elemento raiz que engloba todo o conteúdo da sua página.

- `<head>`: Contém informações sobre o documento, como o título que aparece na aba do navegador.

- `<title>`: Define o título da página que aparece na aba do navegador.

- `<body>`: Contém o conteúdo principal da sua página, como texto, imagens, links, etc.

- `<h1>`: É um cabeçalho (header). HTML tem diferentes níveis de cabeçalhos, como `<h1>`, `<h2>`, `<h3>`, ..., `<h6>`, onde `<h1>` é o maior e mais importante.

- `<p>`: Define um parágrafo. O texto dentro deste elemento será exibido como um parágrafo na página.

HTML é como você estrutura e organiza o conteúdo da sua página web. Cada tag tem um propósito específico, e ao combiná-las, você cria a estrutura da sua página.

Vou mostrar alguns exemplos básicos de HTML para ilustrar diferentes elementos e suas utilizações comuns. Lembre-se de que HTML é uma linguagem de marcação, então as tags fornecem a estrutura básica para o conteúdo da página. Aqui estão alguns exemplos:

1. **Títulos e Parágrafos:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Exemplo HTML</title>
</head>
<body>

    <h1>Título Principal</h1>

    <p>Isto é um parágrafo.</p>

    <h2>Subtítulo</h2>

    <p>Outro parágrafo aqui.</p>

</body>
</html>
```

2. **Listas:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Listas HTML</title>
</head>
<body>

    <h2>Listas</h2>

    <ul>
        <li>Item 1</li>
        <li>Item 2</li>
        <li>Item 3</li>
    </ul>

    <ol>
        <li>Item A</li>
        <li>Item B</li>
        <li>Item C</li>
    </ol>

</body>
</html>
```

3. **Links:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Links HTML</title>
</head>
<body>

    <h2>Links</h2>

    <p>Visite meu <a href="https://www.exemplo.com">site</a>.</p>

</body>
</html>
```

4. **Imagens:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Imagens HTML</title>
</head>
<body>

    <h2>Imagens</h2>

    <img src="imagem.jpg" alt="Descrição da Imagem">

</body>
</html>
```