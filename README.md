# JavaFX

## O que é JavaFX

- JavaFX é uma biblioteca de software para criar interfaces gráficas de usuário (GUIs) em Java.
- Substitui o antigo Swing como principal biblioteca gráfica no Java.
- Permite o desenvolvimento de aplicações desktop e RIAs (Rich Internet Applications) com Java.
- Oferece suporte a diversos tipos de componentes gráficos: botões, tabelas, gráficos, etc.
- Utiliza uma abordagem baseada em cena e nó (*Scene Graph*), onde os elementos gráficos são organizados em uma estrutura de árvore.
- Possui integração com **CSS** para estilização e com **FXML**, um formato XML para descrever a interface.
- Suporta animações, multimídia e a criação de gráficos **2D** e **3D**.
- Funciona em diferentes plataformas: Windows, macOS e Linux.
- Ideal para o desenvolvimento de aplicações como ferramentas de visualização, jogos simples e softwares empresariais.

---

## Como instalar e executar o JavaFX

- Documentação oficial de instalação: <https://openjfx.io/openjfx-docs/>.

---

## A classe `Application` e o método `start`

### Estrutura básica de um aplicativo JavaFX
- Todo aplicativo JavaFX **herda** da classe `Application`.
- O ciclo de vida do aplicativo começa ao executar o método `launch()`.

### Como usar a classe `Application`
- A classe `Application` fornece a base para criar a interface gráfica.
- O método **abstrato** `start()` precisa ser implementado para inicializar a interface.

### O ciclo de vida do método `start()`
- O método `start(Stage primaryStage)` é chamado **após** o `launch()`.
- É responsável por definir o conteúdo principal da janela (**Stage**).

### Ciclo de vida do aplicativo JavaFX
- **Iniciação:** o método `launch()` é chamado.
- **Inicialização:** o método `start()` é chamado para configurar a interface.
- **Execução:** a interface é exibida e interage com o usuário.
- **Encerramento:** quando o usuário fecha a janela ou o sistema encerra o aplicativo.

---

## `Stage` e `Scene` em JavaFX

### Stage — a janela principal
- O `Stage` é a **janela** que pode ser exibida na tela, contendo título, tamanho e conteúdo.
- Pode ser fechado, maximizado, minimizado, e várias janelas (**stages**) podem ser criadas.

### Scene — o conteúdo da janela
- A `Scene` contém os elementos visuais (botões, layouts, textos) exibidos ao usuário.
- Define o tamanho da área de exibição e pode conter um **layout** com vários componentes.

### Relacionamento entre Stage e Scene
- O `Stage` é a **janela** e a `Scene` é o **conteúdo** dentro dessa janela.
- Um `Stage` pode conter **apenas uma** `Scene` de cada vez, mas a `Scene` pode ser trocada dinamicamente durante a execução da aplicação.

---

## O que são Layouts em JavaFX?

- **Layouts** são gerenciadores responsáveis por organizar a posição e o tamanho dos componentes (botões, labels, etc.) dentro de uma interface.
- Controlam como os componentes se **ajustam** ao redimensionamento da janela.
- Garantem **consistência** na apresentação da interface, independentemente do tamanho da tela ou dispositivo.

### Por que usar layouts?
- Evitam posicionar cada componente manualmente.
- Adaptam os componentes de forma eficiente para diferentes resoluções.
- Facilitam o design de interfaces complexas de maneira estruturada e escalável.

### Tipos de layout
- `VBox`, `HBox`, `BorderPane`, `GridPane`.

---

## `VBox` e `HBox` em JavaFX

### VBox — coluna vertical
- Organiza os componentes **em coluna**, de cima para baixo.
- Útil para empilhar elementos como botões, labels e caixas de texto.

### HBox — linha horizontal
- Organiza os componentes **em linha**, da esquerda para a direita.
- Ideal para criar layouts onde os componentes estão lado a lado (ex.: barras de ferramentas).

### Espaçamento e alinhamento
- **Espaçamento:** controla o espaço entre os componentes.
  - Em `VBox`, o espaçamento é **vertical** (entre os elementos empilhados).
  - Em `HBox`, o espaçamento é **horizontal** (entre os elementos lado a lado).
- **Alinhamento:** define como os componentes serão alinhados dentro do contêiner (esquerda, direita, centro, etc.).

---

## `BorderPane` em JavaFX

- O `BorderPane` organiza os componentes em **cinco regiões**:
  - `Top`: parte superior (cabeçalhos, menus).
  - `Bottom`: parte inferior (rodapés, botões de ação).
  - `Left`: lado esquerdo (menus, painéis de navegação).
  - `Right`: lado direito (informações adicionais).
  - `Center`: área central (conteúdo principal da aplicação).
- Cada região pode conter **um único** componente ou layout (botão, texto ou até outro layout).
- Métodos para definir componentes:
  - `setTop()`, `setBottom()`, `setLeft()`, `setRight()`, `setCenter()`.

---

## `GridPane` em JavaFX

- O `GridPane` organiza os componentes em uma **grade** de linhas e colunas.
- Ideal para **formulários**, **tabelas** e layouts com alinhamento preciso.
- Cada célula da grade pode conter um único componente (botões, campos de texto, etc.).
- Para posicionar componentes use `add(node, columnIndex, rowIndex)`, onde:
  - `columnIndex`: a coluna onde o componente será inserido.
  - `rowIndex`: a linha onde o componente será inserido.
- Também é possível fazer o componente **ocupar várias colunas/linhas** com `setColumnSpan()` e `setRowSpan()`.

---

## `StackPane` e `AnchorPane` em JavaFX

### StackPane
- Empilha os componentes **uns sobre os outros**.
- Útil para sobrepor elementos (ex.: texto sobre uma imagem).
- O **último** componente adicionado é exibido no topo.

### AnchorPane
- Permite **ancorar** componentes nas bordas da janela.
- Cada componente pode ser ancorado em **top**, **bottom**, **left** e **right**.
- Útil quando você deseja que os elementos permaneçam fixos ou redimensionados conforme a janela muda de tamanho.

---

## Botões e Labels em JavaFX

### O que são controles?
- **Controles** são componentes interativos usados em interfaces gráficas (botões, caixas de texto, checkboxes, etc.).
- Permitem que o usuário interaja com a aplicação de maneira intuitiva.

### Exemplos comuns de controles
- `Button` (botão)
- `Label` (rótulo de texto)
- `TextField` (campo de texto)

### Criando e configurando
- **Button:** botão clicável.
  - Pode ter texto, ícones, ou ambos.
  - A ação de clique é configurada com um **EventHandler**.
- **Label:** exibe um texto não interativo.
  - Usado para mostrar informações estáticas ou descrever outros controles.

---

## `TextField` e `TextArea` em JavaFX

### Criando campos de texto
- **TextField:** campo de **linha única** (nomes, números). Ideal para entradas curtas.
- **TextArea:** campo de **múltiplas linhas** (descrições, comentários).

### Limite de caracteres
- É possível limitar o número de caracteres com **eventos de texto**.

### Interatividade
- Ambos podem reagir a **eventos de teclado** (pressionar teclas, inserção de texto) e são úteis para captura de dados.

---

## `CheckBox` e `RadioButton` em JavaFX

### CheckBox
- Representa uma caixa de seleção **independente**.
- O usuário pode **selecionar ou desmarcar** várias opções simultaneamente.
- Ideal quando **várias opções** podem ser escolhidas.

### RadioButton
- Usado quando **apenas uma opção** pode ser selecionada **dentro de um grupo**.
- Para funcionar corretamente, os `RadioButton`s devem ser **agrupados** usando um `ToggleGroup`.
- Útil quando o usuário deve **escolher uma única opção** entre várias.

### ToggleGroup
- **Agrupa** `RadioButton`s, garantindo que **apenas uma opção** do grupo possa ser selecionada por vez.
- Todos os `RadioButton`s dentro de um `ToggleGroup` se comportam como uma **escolha única**.

---

## Eventos em JavaFX

### O que são?
- Ações realizadas pelo usuário ou pelo sistema que a aplicação pode **“ouvir”** e responder.

### Exemplos
- **Clique de botão:** quando um botão é pressionado.
- **Movimento do mouse:** movimento/clique em uma área da interface.
- **Teclado:** pressionamento de uma tecla ou combinação de teclas.
- **Mudança de foco:** quando um campo de texto ganha ou perde foco.
- Todo evento gera um **objeto de evento** com informações sobre a ação.

### Modelo de eventos (delegação)
- **Origem do evento:** o componente que gerou o evento (ex.: botão).
- **Objeto de evento:** dados do evento (ex.: `MouseEvent`, `ActionEvent`).
- **Listener/Handler:** bloco de código que responde ao evento.

### Manipulação de eventos (*event handling*)
- Associe o **listener** ao componente (ex.: botão).
- Quando o evento ocorre, o listener é executado.

---

## Eventos de Clique em JavaFX
- Disparados quando o usuário interage com um componente clicável (ex.: botão).
- Evento mais comum: `ActionEvent`, gerado ao clicar em um `Button`.

### Como capturar
- Crie o componente interativo (ex.: `Button`).
- Adicione um `EventHandler` usando `setOnAction(...)`.
- Implemente o código a executar quando o clique ocorrer.

---

## Eventos de Teclado e Mouse em JavaFX

### Teclado
- Captura ações como **pressionar**, **soltar** ou **digitar**.
- Principais eventos:
  - `KeyPressed`
  - `KeyReleased`
  - `KeyTyped` (útil para texto)

### Mouse
- Captura **movimentos** e **cliques**.
- Principais eventos:
  - `MouseClicked`
  - `MouseMoved`
  - `MouseEntered` / `MouseExited`

---

## Tratamento de estilos com CSS em JavaFX
- **CSS** é amplamente utilizado para estilizar componentes de interface no JavaFX.
- Com CSS, é possível modificar **cores**, **fontes**, **margens**, **tamanhos**, e aplicar estilos dinâmicos (foco/hover).
- Benefícios:
  - Personalização organizada e consistente.
  - Separação entre **lógica** e **design**, facilitando a manutenção.
- Estilização pode ser feita via `setStyle()` ou (preferencialmente) por **arquivos CSS externos**.
- Propriedades comuns:
  - `-fx-background-color`
  - `-fx-text-fill`
  - `-fx-padding`
  - `-fx-border-color`, `-fx-border-width`

---

## Criando janelas secundárias em JavaFX
- A janela principal é um `Stage`, e é possível criar janelas **secundárias** (novos `Stage`s).
- Passos:
  - Crie uma nova instância de `Stage`.
  - Defina o conteúdo via `Scene`.
  - Configure título/dimensões.
  - Use `show()` para exibir.

---

## Diálogos de alerta em JavaFX
- `Alert` exibe **caixas de diálogo** com mensagens para o usuário.
- Usos comuns:
  - Informar uma ação.
  - Alertar sobre erros/advertências.
  - Pedir **confirmação**.
- Tipos (`Alert.AlertType`):
  - `INFORMATION`
  - `WARNING`
  - `ERROR`
  - `CONFIRMATION`

---

## Exibindo imagens no JavaFX
- `ImageView` exibe imagens.
- Carregamento:
  - Crie `new Image(path)`.
  - Passe ao `ImageView`.
- Ajustes:
  - `setFitWidth()` / `setFitHeight()`
  - `setPreserveRatio(true)`
- Posicione o `ImageView` em um layout (`VBox`, `HBox`, etc.).

---

## Desenhando formas geométricas em JavaFX
- Classes prontas:
  - `Rectangle`, `Circle`, `Ellipse`, `Line`, `Polygon`, etc.
- Personalização:
  - `setFill()` (preenchimento), `setStroke()` (borda), `setStrokeWidth()`.
- Manipule **tamanho**, **posição** e **estilos**.

---

## Canvas e gráficos 2D em JavaFX
- `Canvas` fornece uma área para **desenho 2D**.
- Use `GraphicsContext` para desenhar:
  - `strokeLine()`, `fillRect()`, `strokeOval()`, `fillText()`, etc.
- Permite desenhar **formas**, **imagens** e **texto**.

---