<svelte:head>
    <title>Solutions To Special Question Section 9</title>
</svelte:head>

<script>
  import EmojiVoter from './emojiVoter.svelte';
  let emojiDict = $state({
      "👍": 0,
      "😍": 0,
      "😡": 0,
  });
</script>

{#each Object.entries(emojiDict) as [emoji, vote]}
    <p>{emoji} {vote}</p>
{/each}

<EmojiVoter {emojiDict} emoji="👍"></EmojiVoter>
<EmojiVoter {emojiDict} emoji="😍"></EmojiVoter>
<EmojiVoter {emojiDict} emoji="😡"></EmojiVoter>
