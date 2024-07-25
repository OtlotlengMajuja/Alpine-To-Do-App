<script>
    export let todos = [];
</script>

<div class="todo-list">
    <slot>
        <p>No todos available</p>
    </slot>
</div>

<div class="todo-items">
    {#each todos as todo}
    ``<slot name="todo" {todo}>
        <div class="todo-item">{todo.text}</div>
      </slot>
    {/each}
</div>

<style>
    .todo-list {
        padding: 10px;
        border: 1px solid #ccc; 
    }

    .todo-items {
        margin-top: 10px;
    }

    .todo-item {
        padding: 5px;
        border-bottom: 1px solid #ccc;
    }
</style>
