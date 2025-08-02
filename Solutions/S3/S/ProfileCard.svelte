<script>
    const {name, imgUrl, bio, highlighted} = $props();
</script>

<div style="border-style: {highlighted ? 'solid' : ''}">
    <p>Name: {name}</p>
    <img src={imgUrl} alt="Url Of Avator">
    <div>
        {bio}
    </div>
</div>
