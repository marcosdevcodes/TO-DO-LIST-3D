# Veja o vídeo como ficou esse projeto...



https://github.com/user-attachments/assets/490682a2-1a95-4c62-96a7-650f415b5491

## Vamos fazer uma explicação do código.
```
let inputBx = document.querySelector("#inputBx");
let list = document.querySelector("#list");

inputBx.addEventListener("keyup", function(evt){
    if(evt.key == "Enter"){
        addItem(this.value)
        this.value = ""
    }

});
```
- inputBx.addEventListener("keyup", function(evt){...}): Aqui, um evento de keyup é adicionado ao campo de entrada (inputBx). Isso significa que a função dentro do addEventListener será executada toda vez que o usuário soltar uma tecla enquanto estiver focado no campo de entrada.
- if(evt.key == "Enter"): Esta linha verifica se a tecla pressionada foi o "Enter". Se for, a função addItem é chamada.
- addItem(this.value): this.value se refere ao valor atual do campo de entrada (inputBx). Ele passa esse valor para a função addItem, que será responsável por adicionar um novo item à lista.
- this.value = "": Depois de adicionar o item à lista, o valor do campo de entrada é redefinido para uma string vazia, limpando o campo para que o usuário possa adicionar uma nova tarefa.

##  Função addItem: Criando e Manipulando um Novo Item de Lista
```
let addItem = (inputBx) => {
    let listItem = document.createElement("li");
    listItem.innerHTML = `${inputBx}<i></i>`;

```

- let addItem = (inputBx) => {...}: Esta é uma função arrow que aceita um argumento inputBx, que é o texto que o usuário digitou.
- let listItem = document.createElement("li");: Um novo elemento <li> é criado dinamicamente. Este elemento será o contêiner de cada nova tarefa.
- listItem.innerHTML = ${inputBx}<i></i>;: O conteúdo HTML do novo <li> é definido como o texto da tarefa (inputBx) seguido por um ícone (<i>).
- O ícone está vazio aqui, mas pode ser estilizado com CSS ou manipulado mais tarde.

## Adicionando a Funcionalidade de Concluir Tarefas
```
listItem.addEventListener("click", function(){
    this.classList.toggle('done');
});

```
- listItem.addEventListener("click", function(){...}): Adiciona um evento de clique a cada item da lista (listItem). Quando o item for clicado, ele será marcado ou desmarcado como concluído.
- this.classList.toggle('done');: Alterna a classe CSS done no item da lista. Esta classe provavelmente aplica um estilo de riscado ou algo similar para indicar que a tarefa foi concluída
##  Adicionando a Funcionalidade de Remover Tarefas
```
listItem.querySelector("i").addEventListener("click", function(){
    listItem.remove();
});

```
- listItem.querySelector("i").addEventListener("click", function(){...}): Adiciona um evento de clique ao ícone <i> dentro do item da lista. Quando o ícone é clicado, o item da lista é removido.
- listItem.remove();: Remove o item da lista completamente do DOM.
  ## Adicionando o Item à Lista
  ```
  list.appendChild(listItem);
  ```
  - list.appendChild(listItem);: Finalmente, o novo item da lista (listItem) é adicionado à lista (list), exibindo-o na página.

## 1 O Usuário Digita uma Tarefa
- Imagine que o usuário abriu uma página da web que contém um campo de input (provavelmente uma caixa de texto) e uma lista (que pode estar vazia no início). O campo de input tem um id="inputBx" e a lista tem um id="list".
- O que o usuário faz: O usuário clica no campo de input e digita uma tarefa, por exemplo, "Comprar leite".
- O que o código faz: À medida que o usuário digita, o evento keyup é acionado para cada tecla que ele solta, mas o código só reage quando o usuário pressiona a tecla "Enter"
## 2 O Usuário Pressiona Enter
- Quando o usuário termina de digitar "Comprar leite" e pressiona a tecla "Enter":
- O que o código faz:
- Evento keyup: O código detecta que a tecla "Enter" foi pressionada.
- Chama addItem: Como a tecla "Enter" foi pressionada, o código chama a função addItem e passa o texto que o usuário digitou ("Comprar leite") como argumento.
- Limpa o Campo de Input: Depois de chamar a função, o código limpa o campo de input, deixando-o pronto para a próxima tarefa que o usuário queira adicionar.
## 3 A Função addItem é Executada
- Agora que a função addItem foi chamada com o valor "Comprar leite":
- O que o código faz:
- Criação do Item de Lista: A função cria um novo elemento <li>, que representará a nova tarefa na lista.
- Define o Conteúdo do Item: O código define o conteúdo do <li> como "Comprar leite" e adiciona um ícone <i> vazio ao lado. Esse ícone será usado para remover a tarefa.
- Adiciona Eventos ao Item:
- Clique no Item: Se o usuário clicar no texto "Comprar leite", o código adiciona ou remove uma classe CSS chamada done, que pode, por exemplo, riscar o texto para indicar que a tarefa foi concluída.
- Clique no Ícone: Se o usuário clicar no ícone <i>, o item de lista é removido completamente da lista.
## 4 O Novo Item Aparece na Lista
- Após a execução da função addItem:
- O que o código faz:
- Adiciona o Item à Lista: O novo <li> (contendo "Comprar leite") é anexado ao final da lista <ul>, tornando-o visível na página.
## 5  Interagindo com a Lista
- Agora, o usuário vê a tarefa "Comprar leite" listada na página.
- O que o usuário pode fazer:
- Marcar como Concluída: O usuário pode clicar no texto "Comprar leite". O código alterna a classe done, que provavelmente aplica um estilo como um texto riscado, indicando que a tarefa - foi concluída.
- Remover a Tarefa: O usuário pode clicar no ícone <i> ao lado de "Comprar leite". O código remove o item de lista da página, excluindo a tarefa.

