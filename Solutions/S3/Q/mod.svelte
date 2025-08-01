<script>
    import Counter from './counter.svelte'
    import ThisLabel from './label.svelte'
    import ColorBox from './ColorBox.svelte'
    import Tag from './Tag.svelte'
    import Nums from './Nums.svelte'
    let showLabel = $state(false);
</script>

<Counter start="10"></Counter>
<button onclick={() => showLabel = !showLabel}>Toggle Label</button>
{#if showLabel}
<ThisLabel labelName="Hello"></ThisLabel>
{/if}
<ColorBox></ColorBox>
<Tag selected="blue"></Tag>
<Nums start=40></Nums>
