<script>
  import TodoList from './lib/ToDoList.svelte';
  let myTodos = ["Write documentation", "Review PRs", "Refactor code"]
</script>

<TodoList todos={myTodos} />

<style>
</style>
