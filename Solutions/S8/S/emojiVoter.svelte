<script>
    let {emojiDict, emoji} = $props();
    const voteEmoji = function() {
      if (!(emoji in emojiDict)) {
        console.error(`Emoji ${emoji} not found in dict`);
        return;
      }

      emojiDict[emoji] += 1;
    }
</script>

<button onclick={voteEmoji}>Vote For {emoji}</button>
