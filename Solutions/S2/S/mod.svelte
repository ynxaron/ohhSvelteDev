<script>
    import Slider from '@bulatdashiev/svelte-slider';
    let text = $state('');
    const colors = ['Red', 'Blue', 'Green', 'Yellow'];
    let thiscolor = $state('Red');
    let value = $state([10, 10]);
    let fontSize = $derived(`${value[0]}px`);
    let inItalics = $state(false);

    const randomizeAll = function() {
      const colorInx = Math.round((Math.random() * 100) % (colors.length - 1));
      thiscolor = colors[colorInx];
      fontSize = `${Math.random() * 30}px`;
      inItalics = Math.random() < 0.5;
    }

    const makeDefaultAll = function() {
      thiscolor = 'Blue';
      fontSize = "10px";
      inItalics = false;
    }
</script>

<input bind:value={text} placeholder="Enter Text Here">
<br>
<br>
<select bind:value={thiscolor}>
    {#each colors as color}
        <option>{color}</option>
    {/each}
</select>
{#if inItalics}
    <p style="color: {thiscolor}; font-size: {fontSize}"><i>{text}</i></p>
{:else}
    <p style="color: {thiscolor}; font-size: {fontSize}">{text}</p>
{/if}

<input type="checkbox" bind:checked={inItalics}>
    <label for="inItalics">inItalics</label>

<Slider bind:value></Slider>

<button onclick={randomizeAll}>Randomize</button>
<button onclick={makeDefaultAll}>Make Default</button>
