<script>
  import TodoList from './lib/ToDoList.svelte';
  let todos = [
    {id: 1, text: "Learn Svelte"},
    {id: 2, text: "Build a project"},
    {id: 3, text: "Deploy the project"}
    ]
</script>

<TodoList {todos}>
  <!-- General slot content -->
  <div slot="header">
    <h2>My To Do List</h2>
    <p>You have{todos.length} todos:</p>
  </div>

  <!-- Content to display when no todos are present-->
  <p slot="no-todos">You have no todos. Add some tasks!</p>

  <!-- Specific slot coontent for each todo item-->
  <div slot="todos">
    {#each todos as todo (todo.id)}
    <div class="custom-todo-item">
      <strong>{todo.text}</strong> (ID: {todo.id})
    </div>
    {/each}
  </div>
</TodoList>

<style>
  .custom-todo-item {
    padding: 5px;
    border: 1px solid #000;
    margin-bottom: 5px;
    padding: 5px;
    border-bottom: 1px solid blue;
    color: blue;
  }
</style>
