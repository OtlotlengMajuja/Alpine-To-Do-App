<script>
  import TodoList from './lib/ToDoList.svelte';
  let todos = [
    {id: 1, text: "Learn Svelte"},
    {id: 2, text: "Build a project"},
    {id: 3, text: "Deploy the project"}
    ]
</script>

<TodoList {todos}>
  <div>
    <h2>My To Do List</h2>
    <p>You have{todos.length} todos:</p>
  </div>

  <div slot="todo" let:todo>
    <div class="custom-todo-item">
      <strong>{todo.text}</strong> (ID: {todo.id})
    </div>
  </div>
</TodoList>

<style>
</style>
