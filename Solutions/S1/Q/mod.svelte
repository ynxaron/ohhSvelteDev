<script>
    import Slider from '@bulatdashiev/svelte-slider';
    let name = $state("Satyam");
    let times_clicked = $state(0);
    let night_mode = $state(false);
    let fruits = ["Apple", "Mango", "Banana", "Lizards", "Grapes"];
    let value = $state([10, 10]);
    let greetFontSize = $derived(`${value[0]}px`);
</script>
<p style="font-size: {greetFontSize}">Hello {name}!</p>
<Slider bind:value/>
<p>The Number Of Times You Have clicked this button is: {times_clicked}</p>
<button onclick={() => times_clicked += 1}>Click To Increment</button>
<button onclick={() => night_mode = !night_mode}>Toggle Night Mode</button>
{#if night_mode}
    <p>You Have Toggled Night Mode</p>
{:else}
    <p>You Have Toggled Day Mode</p>
{/if}
<input type="text" bind:value={name}>
{#if times_clicked > 5}
    <p>You Have clicked the button more than five times</p>
{/if}
{#if fruits.length == 0}
    <p>The Fruit Length is 0</p>
{/if}
<ul>
    {#each fruits.filter((fruit) => fruit.includes('a')) as fruit}
        <p>You Have Eaten {fruit} Now</p>
    {/each}
</ul>

<style>
</style>
