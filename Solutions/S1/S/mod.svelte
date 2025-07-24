<script>
    let name = $state('');
    let tone_formal = $state(false);
    let all_shown = $state(true);
</script>

<button onclick={() => tone_formal = !tone_formal}>Toggle Formal</button>
<input bind:value={name} placeholder="Enter Name">
{#if all_shown}
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
{/if}

<button onclick={() => all_shown = !all_shown}>Hide/Show All</button>
