<script>
    import Slider from '@bulatdashiev/svelte-slider';
    import moment from 'moment';
    let count = $state(0);

    let double = $derived(count * 2);
    let quadriple = $derived(count * 4);

    let length = $state(0);
    let width = $state(0);

    let area = $derived(length * width);

    let value = $state([0, 0]);
    let fontSize = $derived(`${value[0]}px`);

    let clickedMoment = $state(null);
    let timePassed = $derived(`${moment().diff(clickedMoment)}s`);

    let names = $state([]);
    let currentName = $state('');

    $effect(() => console.log(`The Value Changed. Length: '${length}\nWidth: '${width}'`));
</script>

<input bind:value={length} placeholder="Enter Length">
<input bind:value={width} placeholder="Enter Width">

<p>The Area Is: {area}</p>

<p>Double is {double} and quadriple is {quadriple}</p>
<button onclick={() => count += 1}>Increment</button>

<p style="font-size: {fontSize};">This Size Changes</p>

<Slider bind:value></Slider>

{#if clickedMoment}
    <p>Total Time Passed Since You Clicked Bellow Button Is: {timePassed}</p>
{/if}

{#if count <= 6}
    <p>The Count Is Less than 7</p>
{:else}
    <p>The Count Is More than or equal to 7</p>
{/if}

<input type="text" bind:value={currentName} placeholder="Enter New Name">
<br>
<button onclick={() => names.push(currentName)}>Add Name</button>

<div>
    {#if names.length == 0}
        <p>Names Array Is Empty</p>
    {:else}
        <p>Total Names Are: {names}</p>
    {/if}
</div>

<br>
<br>

<button onclick={() => {
  clickedMoment = moment();
}}>Instantiate Time</button>
