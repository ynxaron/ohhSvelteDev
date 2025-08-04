<script>
    let {loginData} = $props();
    const verifyData = function() {
      if ((loginData.username != "") && (loginData.passwd != "") && (loginData.age != 0)) {
        loginData.isReady = true;
      }
    }
</script>

<input bind:value={loginData.username} placeholder="Enter UserName">
<input bind:value={loginData.passwd} placeholder="Enter Password">
<input bind:value={loginData.age} placeholder="Enter Age">

<button onclick={verifyData}>Verify Data</button>
