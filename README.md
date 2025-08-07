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
