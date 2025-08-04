<svelte:head>
    <title>BMI Calculater</title>
</svelte:head>

<script>
    let bodyInfo = $state({height: null, weight: null});
    let bmi = $derived(bodyInfo.height / (bodyInfo.weight ** 2))
</script>

<input type="text" placeholder="Enter Height" bind:value={bodyInfo.height}>
<input type="text" placeholder="Enter Weight" bind:value={bodyInfo.weight}>

<div>
    <p>Given Your Body Info, Your BMI is: {bmi}</p>
    {#if bmi > 12}
        <p>You are a fatty!</p>
    {:else}
        <p>You are pretty cool</p>
    {/if}
</div>
