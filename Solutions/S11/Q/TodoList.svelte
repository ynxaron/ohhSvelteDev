<script>
    let {todos = []} = $props();
</script>

<ul>
    {#each todos as todo}
        <li>{todo}</li>
    {/each}
</ul>
