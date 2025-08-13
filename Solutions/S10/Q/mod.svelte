<script>
    let c1 = $state(0);
    let c2 = $state(0);

    let sum = $derived(c1 + c2);
    let thriceSum = $derived(sum * 3);

    let userInfo = $state({
      name: '',
      age: 0
    });

    let itemsArr = $state([]);
    let item = $state(null);
    let greeting = $derived(`The Name Is: ${userInfo.name} and Age Is: ${userInfo.age}`);
</script>

<p>The Sum Is: {sum}</p>
<div>
    <input placeholder="Enter Name" bind:value={userInfo.name}>
    {#if userInfo.name.length > 10}
        <p style="color:Red">Make Sure Your Name Is Less Than 10 characters long</p>
    {/if}
    <input placeholder="Enter Age" bind:value={userInfo.age}>
</div>
<p>{greeting}</p>

<ul>
    {#each itemsArr as item}
        <li>{item}</li>
    {/each}
    <br>
</ul>

<p>You Have {itemsArr.length} items in your array</p>
<input placeholder="Enter Item" bind:value={item}>
<button onclick={() => itemsArr.push(item)}>Add Item</button>
