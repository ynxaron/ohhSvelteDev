<script>
    let profileInfo = {
      avatar: '~/code/newAtten/code/assets/djubo-cropped.png',
      name: 'Satyam',
      bio: 'A Hacker In Spirit, otherwise unemployed',
      isonline: true // always
    }

    import ProfileCard from './ProfileCard.svelte';
</script>

<ProfileCard {profileInfo}></ProfileCard>
