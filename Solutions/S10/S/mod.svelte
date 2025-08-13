<svelte:head>
    <title>Tipping Calculater</title>
</svelte:head>

<script>
    let billInfo = $state({
      totalBill: 0,
      tipPercent : 0,
      noOfPeople: 0,
    });

    let tipInfo = $derived({
      totalTip: billInfo.totalBill * billInfo.tipPercent,
      grandTotal: (billInfo.totalBill * billInfo.tipPercent) + billInfo.totalBill,
      perPerson : tipInfo.grandTotal / billInfo.noOfPeople,
    });

    const isValid = function() {
      return (billInfo.totalBill && billInfo.tipPercent && billInfo.noOfPeople)
    }
</script>

<form>
    <input placeholder="Total Bill" bind:value={billInfo.totalBill}>
    <input placeholder="Tip Percentage" bind:value={billInfo.tipPercent}>
    <input placeholder="No Of People" bind:value={billInfo.noOfPeople}>
    {#if isValid()}
    <div>
        <h2>Bill Information</h2>
        <p>The Total Bill (+ tips) is: {tipInfo.grandTotal}Rs</p>
        <p>Your Bill Was: {billInfo.totalBill} and you paid {tipInfo.totalTip}Rs</p>
        <p>Each Of You Shall Be Paying (for tips): {tipInfo.perPerson}</p>
    </div>
    {:else}
        <div>
            <p style="color: Red">Enter All Information First</p>
        </div>
    {/if}
   </form>
