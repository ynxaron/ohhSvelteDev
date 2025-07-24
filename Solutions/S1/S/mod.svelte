<script>
    let name = $state('');
    let tone_formal = $state(false);
</script>

<button onclick={() => tone_formal = !tone_formal}>Toggle Formal</button>
<input bind:value={name} placeholder="Enter Name">
{#if name}
    {#if tone_formal}
        <p>Grettings, {name}</p>
    {:else}
        <p>Hi, {name}</p>
    {/if}
{:else}
    {#if tone_formal}
        <p>Welcome!</p>
    {:else}
        <p>Hi There!</p>
    {/if}
{/if}
