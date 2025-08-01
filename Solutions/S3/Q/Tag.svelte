<script>
    const {selected} = $props();
</script>

<style>
    .Selected {
        background-color: blue;
        color: white;
    }
</style>

<p class={selected == "blue" ? 'Selected' : ''}>Speaking For Tag</p>
