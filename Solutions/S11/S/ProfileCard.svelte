<script>
    let {profileInfo} = $props();
    let {avatar, name, bio, isonline} = profileInfo;
</script>

<div>
    <img alt="User / Avator" src={avatar}>
    <p>The Name Is: {name}</p>
    <p>{bio}</p>
    {#if isonline}
        <p>Is Online</p>
    {:else}
        <p>Is Offline</p>
    {/if}
</div>
