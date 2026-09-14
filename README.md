### 🛠️ Funcionalidades dos Botões (JavaScript)

O projeto utiliza JavaScript para manipular o DOM e adicionar interatividade aos botões da página. Abaixo estão as funções implementadas:

#### 1. Alternador de Tema (Dark/Light Mode)
Esta função escuta o clique no botão de tema e alterna a classe `whitemode` no `body`, mudando o visual do blog.
```javascript
const botaotema = document.getElementById("troca-tema");

if (botaotema) {
    botaotema.addEventListener("click", () => {
        // Adiciona ou remove a classe do body
        document.body.classList.toggle("whitemode");
        console.log("WhiteMode Escolhido?", document.body.classList.contains("whitemode"));
    });
}
```

#### 2. Sistema de Likes e Reações
Esta função gerencia as curtidas nos posts. Ela adiciona um evento de clique para cada botão de reação, incrementa o contador ao clicar e decrementa caso o usuário desfaça a ação (com validação para ignorar o botão de tema).
```javascript
const botoes = document.querySelectorAll("button");

botoes.forEach(function(botao) {
    // Ignora o botão de tema para não contar like nele
    if (botao.id === "troca-tema") return; 

    let curtiu = false;
    botao.addEventListener("click", botaoClicado);

    function botaoClicado() {
        console.log("fui clicado");
        let texto = botao.querySelector("span");
        if (curtiu == false) {
            texto.textContent++;
            curtiu = true;
        } else {
            texto.textContent--;
            curtiu = false;
        }
    }
});
```
