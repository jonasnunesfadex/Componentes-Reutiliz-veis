# Aula-Componentes-HTML-Reutiliz-veis-em-JavaScript

## Objetivos da Aula

Ao final da aula, o aluno deverá ser capaz de:

 - Entender o conceito de componentes reutilizáveis;

 - Criar elementos HTML dinamicamente com JavaScript;

 - Reaproveitar código para evitar repetição;

 - Trabalhar com funções que geram componentes;

 - Inserir componentes no DOM;

 - Criar interfaces mais organizadas e escaláveis


## index.html

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Compontes reutilizáveis</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <nav id="menu"></nav>

    <p class="paragrafo">Página incial</p>

    <div id="conteudo"></div>

    <script src="script.js"></script>
    
</body>
</html>
```

## produtos.html
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Compontes reutilizáveis</title>
    <link rel="icon" type="image/png" href="image2.png">
    <link rel="stylesheet" href="style.css">
    
</head>
<body>

    <nav id="menu"></nav>
    
    <p class="paragrafo">Página Produtos</p>

    
    <div id="conteudo"></div>

    <script src="script.js"></script>
    
      <script>
        conteudo.innerHTML = criarCard(
        "Produtos",
        "Veja nossos produtos disponíveis."
    );
    </script>

</body>
</html>
```

## contato.html
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Compontes reutilizáveis</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <nav id="menu"></nav>
    
    <p class="paragrafo">Página Contatos</p>

    <div id="conteudo"></div>

    <script src="script.js"></script>

    <script>
        conteudo.innerHTML = criarCard(
        "Contatos",
        "Entre em contato conosco. empresa@gmail.com"
    );
    </script>
    
</body>
</html>
```
## script.js

```js
function criarBotaoMenu(texto, link) {

    return `
        <a href="${link}" class="botao-menu">
            ${texto}
        </a>
    `;
}

const menu = document.getElementById("menu");

menu.innerHTML += criarBotaoMenu("Início", "index.html");
menu.innerHTML += criarBotaoMenu("Produtos", "produtos.html");
menu.innerHTML += criarBotaoMenu("Contato", "contato.html");

function criarCard(titulo, texto) {

    return `

        <div class="card">

            <h2>${titulo}</h2>

            <p>${texto}</p>

        </div>

    `;
}

const conteudo = document.getElementById("conteudo");

conteudo.innerHTML = criarCard(
    "Bem vindo",
    "Esse é um card reutilizável criado com JavaScript."
);

```

##  style.css

```css
.paragrafo{
    padding: 20px;
    border-radius: 10px;
    background-color: #f4f4f4;
    text-align: center;
}

#menu {
    display: flex;
    justify-content: center;
    gap: 15px;
    margin-bottom: 30px;
}

.botao-menu {
    padding: 12px 20px;
    border: none;
    border-radius: 8px;
    background-color: #222;
    color: white;
    font-size: 16px;
    cursor: pointer;
    transition: 0.3s;
}

.botao-menu:hover {
    background-color: #0077ff;
    transform: scale(1.05);
}

.botao-menu {
    padding: 12px 20px;
    border-radius: 8px;
    background-color: #222;
    color: white;

    text-decoration: none;

    font-size: 16px;

    transition: 0.3s;
}

.botao-menu:hover {
    background-color: #0077ff;
}

#conteudo {
    display: flex;

    justify-content: center;

    margin-top: 50px;
}

.card {

    width: 300px;

    padding: 20px;

    border-radius: 10px;

    background-color: #f4f4f4;

    box-shadow: 0 0 10px rgba(0,0,0,0.2);

    text-align: center;
}

.card h2 {
    margin-bottom: 10px;
}

```
