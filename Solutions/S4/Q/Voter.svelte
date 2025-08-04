<script>
    let {votingData, votingTag} = $props();
    const updateVotingData = function() {
      if (!Object.hasOwn(votingData, votingTag)) {
        console.error(`The Tag '${votingTag}' not in voting data`);
        return;
      }
      votingData[votingTag] += 1;
      console.log(votingData);
    }
</script>

<input type="checkbox" onclick={updateVotingData}>
<label>{votingTag}</label>
