<script>
    import Voter from './Voter.svelte';
    const votingTags = ['Wow', 'Yes', 'Good', 'Nice'];
    let votingTag1 = $state(votingTags[0]);
    let votingTag2 = $state(votingTags[1]);
    let votingTag3 = $state(votingTags[2]);
    let votingTag4 = $state(votingTags[3]);
    let votingDataRaw = {};
    votingTags.forEach((voteTag, _) => {
      votingDataRaw[voteTag] = 0;
    })
    let votingData = $state(votingDataRaw);
    console.log(votingData);
</script>

<Voter {votingData}, votingTag={votingTag1}></Voter>
<Voter {votingData}, votingTag={votingTag2}></Voter>
<Voter {votingData}, votingTag={votingTag3}></Voter>
<Voter {votingData}, votingTag={votingTag4}></Voter>
