<script>
  import TodoList from './lib/ToDoList.svelte';
  let todos = [
    {id: 1, text: "Learn Svelte"},
    {id: 2, text: "Build a project"},
    {id: 3, text: "Deploy the project"}
    ]
</script>

<TodoList todos={myTodos} />

<style>
</style>
