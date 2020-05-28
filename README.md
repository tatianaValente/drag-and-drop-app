Projeto criado em React para desenvolver um Drag and Drop usando a biblioteca React Beautiful DND (https://github.com/atlassian/react-beautiful-dnd)

## React Beautiful DND

### Criação de um novo projeto em React:
`npx create-react-app task-app`

### Adição da biblioteca de drag and drop:
`npm add react-beatuful.dnd`

### Componentes da biblioteca:
#### `<DragDropContext />` - Agrupa a parte do seu aplicativo que você deseja ativar e arrastar para.
##### Props obrigatórios:
- onDragEnd : função a ser executada quando 

####`<Droppable />` - Área em que pode solto o componente arrastado. Contém <Draggable /> s dentro dele. 
##### Props obrigatórios:
-	innerRef: (?HTMLElement) => void – elemento do DOM
-	 droppableProps: DroppableProps - Este é um objeto que contém propriedades que precisam ser aplicadas a um elemento solto na tela.
-	 placeholder: ?Node - É usado para criar espaço no <Droppable /> conforme necessário durante um arrasto
##### Exemplo:
`<Droppable droppableId="droppable-1">
    {(provided, snapshot) => (
        <div ref={provided.innerRef} {...provided.droppableProps}>
            Good to go(Aqui deve ter um elemento <Draggable />)
            {provided.placeholder}
        </div>
    )}
</Droppable>`

####`<Draggable />` - O que pode ser arrastado.

`resetServerContext()` - Utilitário para renderização do lado do servidor



