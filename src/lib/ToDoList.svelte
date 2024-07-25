<script>
    export let todos = [];
</script>

<div class="todo-list">
    <slot name="header">
        <!-- Default slot content for header -->
        <p>No todos available</p>
    </slot>
</div>

<div class="todo-items">
    {#if todos.length > 0}
    ``<slot name="todos">
        <!-- Default content for each todo item if no named slot is provided -->
        {#each todos as todo (todo.id)}
            <div class="todo-item">{todo.text}</div>
        {/each}
      </slot>
    {:else}
        <!-- Slot for when there are no todos -->
        <slot name="no-todos">
            <!-- Default content if no slot content is provided -->
            <p>No todos to display</p>
        </slot>
  {/if}
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
