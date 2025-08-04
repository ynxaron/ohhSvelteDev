<script>
    let {thiscolor} = $props()
    const colors = ['Red', 'Blue', 'Green']
</script>

<select bind:value={thiscolor.color}>
    {#each colors as color}
        <option>{color}</option>
    {/each}
</select>
