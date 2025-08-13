<script>
    let {highlighted} = $props();
</script>

<style>
    .ImpText {
        color: red;
        background-color: white;
    }
</style>

<div class={highlighted ? 'ImpText' : ''}>
    <p>Hello There</p>
</div>
