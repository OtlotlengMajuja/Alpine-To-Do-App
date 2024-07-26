<script>
    import { createEventDispatcher } from "svelte";
    export let todos = [];

    const dispatch = createEventDispatcher();

    function handleTodoClick(todo) {
        dispatch("todoClick", todo);
    }
</script>

<slot name="header"></slot>

{#if todos.length === 0}
  <slot name="no-todos"></slot>
{:else}
  <slot name="todos">
    {#each todos as todo (todo.id)}
      <div class="todo-item" on:click={() => handleTodoClick(todo)} role="button" tabindex="0" on:keydown={(e) => e.key === 'Enter' || e.key === ' ' ? handleTodoClick(todo) : null}>
        {todo.text}
      </div>
    {/each}
  </slot>
{/if}

<style>
    .todo-item {
        padding: 5px;
        border: 1px solid #ccc;
        margin-bottom: 5px;
        cursor: pointer;
    }
</style>
