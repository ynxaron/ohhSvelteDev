<script>
    let {color = "skyblue", highlighted} = $props();
    highlighted = (highlighted == "true");
</script>

<p style="background-color: {color}; border: {highlighted ? 'solid' : 'thin'}">Hello There</p>
