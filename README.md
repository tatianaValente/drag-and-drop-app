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

#### `<Droppable />` - Área em que pode solto o componente arrastado. Contém <Draggable /> s dentro dele. 
##### Props obrigatórios:
-	droppableId 

##### Provided (DroppableProvided):
-	innerRef: (?HTMLElement) => void – elemento do DOM
-	droppableProps: DroppableProps - Este é um objeto que contém propriedades que precisam ser aplicadas a um elemento solto na tela.
-	placeholder: ?Node - É usado para criar espaço no <Droppable /> conforme necessário durante um arrasto

##### Exemplo:
`<Droppable droppableId="droppable-1">

    {(provided, snapshot) => (
    
        <div ref={provided.innerRef} {...provided.droppableProps}>
        
            Good to go(Aqui deve ter um elemento <Draggable />)
            
            {provided.placeholder}
            
        </div>
        
    )}
    
</Droppable>`

#### `<Draggable />` - O que pode ser arrastado.

##### Props obrigatórios:
-	draggableId
-	índice - Um requerido number que corresponda à ordem do <Draggable />no <Droppable />. É simplesmente o índice da <Draggable />na lista.

##### Provided (DraggableProvided):
-	innerRef: (?HTMLElement) => void – elemento do DOM
-	draggableProps : DraggableProps - é um objeto que contém um dataatributo e uma linha style. Controla o movimento do arrastável quando está arrastando e não arrastando.
-	dragHandleProps :? DragHandleProps - É usado para arrastar o todo <Draggable />
##### Exemplo:
'<Draggable draggableId={this.props.task.id} index={this.props.index}>
    {provided => (
        <Container
            {...provided.draggableProps}
            {...provided.dragHandleProps}
            ref={provided.innerRef}
        >
            {this.props.task.content}
        </Container>
    )}
</Draggable>'

#### `resetServerContext()` 
Função deve ser usada quando a renderização do lado do servidor (SSR). Ele garante que o estado do contexto não persista em várias renderizações no servidor, o que resultaria em incompatibilidades de marcação de cliente / servidor depois que várias solicitações forem renderizadas no servidor.



