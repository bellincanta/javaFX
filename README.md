# Java FX

## O que é Java FX

- JavaFX é uma biblioteca de software para criar interfaces gráficas de usuário (GUIs) em Java;
- Substitui o antigo Swing como principal biblioteca gráfica no Java;
- Permite o desenvolvimento de aplicações desktop e RIAs (Rich Internet Applications) com Java;
- Oferece suporte a diversos tipos de componentes gráficos: botões, tabelas, gráficos, etc;
- Utiliza uma abordagem baseada em cena e nó (Scene Graph), onde os elementos gráficos são organizados em uma estrutura de árvore;
- Possui integração com CSS para estilização e com FXML, um formato XML para descrever a interface;
- Suporta animações, multimídia e a criação de gráficos 2D e 3D;
- Funciona em diferentes plataformas: Windows, Mac e Linux;
- Ideal para o desenvolvimento de aplicações, como ferramentas de visualização, jogos simples e softwares empresariais;

---

## Como instalar e executar o JavaFX

- Documentação oficial de instalação: [https://openjfx.io/openjfx-docs/](https://openjfx.io/openjfx-docs/)
- Baixar o JavaFX no site oficial e extrair os arquivos para uma pasta;
- Abrir o VS Code e criar uma pasta para o projeto;
- Acessar a opção `Help -> Show All Commands -> Create Java Project`, e selecionar `No build tools`;
- Selecionar a pasta pai (pasta do projeto) e nomear o projeto, por exemplo: `HelloWorldFX`;
- Em *Java Projects*, adicionar os arquivos do JavaFX em `Referenced Libraries`;
- Deletar o arquivo criado automaticamente com o nome `App.java`;
- Criar uma pasta com o nome do projeto dentro de `src`, exemplo: `helloworldfx`;
- Adicionar os arquivos `Main`, `FXML` e `Controller`, fornecidos pela documentação;
- Na aba `Run and Debug` do VS Code, selecionar a opção `Create json file`;
- Configurar o valor de `vmArgs` no `launch.json`, conforme a documentação indica;

---

## A Classe Application e o Método Start

### Estrutura Básica de um Aplicativo JavaFX

- Todo aplicativo JavaFX herda da classe `Application`;
- O ciclo de vida do aplicativo começa ao executar o método `launch()`;

### Como Usar a Classe Application

- A classe `Application` fornece a base para criar a interface gráfica;
- O método abstrato `start()` precisa ser implementado para inicializar a interface;

### O Ciclo de Vida do Método start()

- O método `start(Stage primaryStage)` é chamado após o `launch()`;
- É responsável por definir o conteúdo principal da janela (`Stage`);

### O ciclo de vida do aplicativo JavaFX:

1. **Iniciação:** O método `launch()` é chamado;
2. **Inicialização:** O método `start()` é chamado para configurar a interface;
3. **Execução:** A interface é exibida e interage com o usuário;
4. **Encerramento:** Quando o usuário fecha a janela ou o sistema encerra o aplicativo;

---

## Stage e Scene em JavaFX

### Stage: Representa a janela principal da aplicação JavaFX

- O `Stage` é a janela que pode ser exibida na tela, contendo o título, o tamanho e o conteúdo;
- Pode ser fechado, maximizado, minimizado, e várias janelas (`Stages`) podem ser criadas;

### Scene: Representa o conteúdo dentro de um Stage

- A `Scene` contém os elementos visuais (botões, layouts, textos) que serão exibidos ao usuário;
- Define o tamanho da área de exibição e pode conter um layout com vários componentes;

### Relacionamento entre Stage e Scene

- O `Stage` é a "janela", e a `Scene` é o "conteúdo" dentro dessa janela;
- Um `Stage` pode conter apenas uma `Scene` de cada vez, mas essa `Scene` pode ser trocada dinamicamente durante a execução da aplicação;

---

## O que são Layouts em JavaFX?

- **Layouts** são gerenciadores responsáveis por organizar a posição e o tamanho dos componentes (botões, *labels*, etc.) dentro de uma interface;
- Controlam como os componentes se ajustam ao redimensionamento da janela;
- Garantem consistência na apresentação da interface, independentemente do tamanho da tela ou dispositivo.

### Por que usar Layouts?
- Evitam a necessidade de posicionar cada componente manualmente;
- Adaptam os componentes de forma eficiente para diferentes resoluções;
- Facilitam o design de interfaces complexas de maneira estruturada e escalável.

### Tipos de layout mais comuns
- `VBox`, `HBox`, `BorderPane`, `GridPane`.

---

## VBox e HBox em JavaFX

- **VBox:** organiza os componentes em uma coluna (de cima para baixo). Útil para empilhar elementos como botões, *labels* e caixas de texto em uma disposição vertical;
- **HBox:** organiza os componentes em uma linha (da esquerda para a direita). Ideal para criar layouts onde os componentes estão lado a lado, como uma barra de ferramentas ou grupo de opções;
- **Espaçamento (*spacing*):** controla o espaço entre os componentes. Em `VBox`, o espaçamento é **vertical**; em `HBox`, é **horizontal**;
- **Alinhamento (*alignment*):** define como os componentes serão alinhados dentro do contêiner (esquerda, direita, centro ou ajustado ao conteúdo).

---

## BorderPane em JavaFX

- O `BorderPane` organiza os componentes em cinco regiões:
  - **Top**: parte superior (cabeçalhos, menus);
  - **Bottom**: parte inferior (rodapés, botões de ação);
  - **Left**: lado esquerdo (menus/painéis de navegação);
  - **Right**: lado direito (informações adicionais/detalhes);
  - **Center**: área central (conteúdo principal da aplicação).
- Cada região pode conter um único componente ou outro *layout* (por exemplo, um `HBox` dentro de `Top`);
- Use os métodos `setTop()`, `setBottom()`, `setLeft()`, `setRight()` e `setCenter()` para definir os componentes em cada região.

---

## GridPane em JavaFX

- `GridPane` organiza os componentes em uma **grade de linhas e colunas**;
- Ideal para criar **formulários**, **tabelas** e layouts com alinhamento preciso;
- Cada célula da grade pode conter um único componente (botões, campos de texto, etc.);
- Para posicionar componentes, use `add(node, columnIndex, rowIndex)`, onde:
  - `columnIndex`: posição da **coluna** onde o componente será inserido;
  - `rowIndex`: posição da **linha** onde o componente será inserido;
- É possível fazer o componente ocupar várias colunas/linhas com `GridPane.setColumnSpan(node, span)` e `GridPane.setRowSpan(node, span)` (ou definindo *constraints* com *colspan*/*rowspan*).

---

## StackPane e AnchorPane em JavaFX

- **StackPane** empilha os componentes **uns sobre os outros**;
  - Útil para sobrepor elementos (ex.: texto sobre uma imagem);
  - O último componente adicionado fica no topo;
- **AnchorPane** permite **ancorar (fixar)** componentes nas bordas da janela;
  - Cada componente pode ser ancorado em uma ou mais bordas (*top*, *bottom*, *left*, *right*);
  - Útil quando você deseja que elementos permaneçam fixos ou redimensionem conforme a janela muda de tamanho.

---

## Botões e Labels em JavaFX

### O que são controles?
- **Controles** são componentes interativos usados em interfaces gráficas (botões, caixas de texto, *checkboxes*, etc.);
- Permitem que o usuário interaja com a aplicação de maneira intuitiva.

### Exemplos comuns
- `Button` (botão)
- `Label` (rótulo de texto)
- `TextField` (campo de texto)

### Criando e configurando
- **Button:** representa um botão clicável; pode ser configurado com texto, ícones ou ambos. A ação de clique é configurada com um `EventHandler` (por exemplo, `setOnAction(...)`);
- **Label:** exibe um rótulo de texto **não interativo**; usado para mostrar informações estáticas ou descrever outros controles.

---

## TextField e TextArea em JavaFX

- **TextField:** campo de texto de **linha única**, usado para entradas simples (nomes, números). Ideal para entradas curtas;
- **TextArea:** campo de texto de **múltiplas linhas**, usado para entradas longas (descrições, comentários);
- **Limite de caracteres:** é possível limitar a quantidade de caracteres usando *listeners* de texto (por exemplo, ouvindo mudanças na propriedade `textProperty()`);
- **Interatividade:** ambos podem reagir a eventos de teclado (pressionar teclas, inserção de texto) e são comumente usados na captura de dados.

## CheckBox e RadioButton em JavaFX

### CheckBox
- Representa uma caixa de seleção **independente**;
- O usuário pode **selecionar ou desmarcar** várias opções simultaneamente;
- Ideal quando **várias opções** podem ser escolhidas;

### RadioButton
- Usado quando **apenas uma opção** pode ser selecionada **dentro de um grupo** de opções;
- Para funcionar corretamente, os `RadioButton`s devem ser **agrupados** usando um `ToggleGroup`;
- Útil quando o usuário deve **escolher uma única opção** entre várias;

### ToggleGroup
- Um `ToggleGroup` é usado para **agrupar** `RadioButton`s, garantindo que **apenas uma opção** dentro do grupo possa ser selecionada por vez;
- Todos os `RadioButton`s dentro de um `ToggleGroup` se comportam como uma **escolha única** (ou seja, **só pode haver um selecionado** ao mesmo tempo);
---

## Eventos em JavaFx

● O que são eventos em JavaFX?
○ Eventos são ações realizadas pelo usuário ou pelo sistema que a aplicação pode "ouvir" e responder;

● Exemplos de eventos:
○ Clique de botão: Quando um botão é pressionado pelo usuário;
○ Movimento do mouse: O movimento ou clique do mouse em uma área da interface;
○ Teclado: Pressionamento de uma tecla ou combinação de teclas;
○ Mudança de foco: Quando um campo de texto ganha ou perde foco;
○ Cada evento gera um objeto de evento que contém informações sobre a ação realizada;

● Modelo de eventos em JavaFX segue o padrão Delegação de Eventos, onde o evento é capturado e encaminhado para o manipulador correto:
○ Origem do evento: O componente que gera o evento, como um botão;
○ Objeto de evento: A informação sobre o evento (ex.: MouseEvent, ActionEvent);
○ Listener/Handler (Manipulador de Evento): Um bloco de código que responde ao evento;

● Event Handling (Manipulação de Eventos):
○ O listener ou handler é associado ao componente (ex.: botão) que deseja capturar o evento;
○ Quando o evento ocorre, o listener é chamado para executar o código associado;


## Eventos de Clique em JavaFX

● Eventos de clique são capturados quando o usuário interage com um botão, pressionando-o e soltando-o;
● O evento mais comum é o ActionEvent, que é gerado ao clicar em um botão;
● Para lidar com eventos de clique, usamos event handlers ou listeners, que são blocos de código associados ao componente (botão);

● Passos para Capturar um Evento de Clique:
○ Criar o componente interativo (ex.: Button);
○ Adicionar um EventHandler usando o método setOnAction() do botão;
○ Implementar o código que deve ser executado quando o evento de clique ocorre;


## Eventos de Teclado e Mouse em JavaFX

● Eventos de Teclado:
○ Capturam ações do usuário relacionadas ao teclado, como pressionar, soltar ou digitar uma tecla;

● Principais eventos:
○ KeyPressed: Quando uma tecla é pressionada;
○ KeyReleased: Quando uma tecla é liberada;
○ KeyTyped: Quando uma tecla é digitada (geralmente usado para texto);

● Eventos de Mouse:
○ Capturam interações do usuário com o mouse, como movimento e cliques;

● Principais eventos:
○ MouseClicked: Quando o mouse é clicado;
○ MouseMoved: Quando o mouse é movido;
○ MouseEntered/MouseExited: Quando o ponteiro do mouse entra ou sai de um componente;
