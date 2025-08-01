<script>
    const props = $props();
    const start = Number(props.start);
    const numbers =
      [...Array(10).keys().map((n) => n + start)];
</script>

{#each numbers as num}
    <p>Count Is: {num}</p>
{/each}
