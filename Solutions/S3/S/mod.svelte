<script>
    import ProfileCard from './ProfileCard.svelte';
    const bio1 = "He is a good good man";
    const bio2 = "He is a bad man";
</script>

<ProfileCard name="Satyam" bio={bio1} imgUrl="~/code/newAtten/code/assets/fifth_profile_round.png" highlighted></ProfileCard>
<ProfileCard name="Aron" imgUrl="/home/ynx/code/newAtten/code/assets/fourth_profile_round.png" bio={bio2}></ProfileCard>
