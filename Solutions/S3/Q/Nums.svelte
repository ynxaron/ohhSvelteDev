<script>
    const {start = 0} = $props();
    const calculated = $derived(start * 2);
</script>

<p>The Value Is: {calculated}</p>
