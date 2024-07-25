<script>
    export let todos = ["Learn Svelte", "Build an app"];
</script>

<h1>To Do List</h1>

<ul>
    {#each todos as todo}
    <li>{todo}</li>
    {/each}
</ul>