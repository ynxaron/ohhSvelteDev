<script>
  let {count} = $props();
</script>

<button onclick={() => count.value += 1}>Add Count</button>
<p>INSIDE: Count: {count.value}</p>
