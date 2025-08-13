<script>
    let formInfo = $state({
      name: '',
      email: '',
      message: ''
    });

    const validateForm = function() {
      return (formInfo.name.length && formInfo.email.length && formInfo.message.length);
    }
</script>

<form>
    <label for="name">Hello {formInfo.name}</label>
    <input placeholder="Enter Name" bind:value={formInfo.name}>
    <br>
    <label for="email">Mail To {formInfo.email}</label>
    <input placeholder="Enter Mail" bind:value={formInfo.email}>
    <br>
    <label for="message">Enter Your Message</label>
    <input placeholder="Enter Message" bind:value={formInfo.message}>
    <br>
    {#if validateForm()}
        <input type="Submit">
    {:else}
        <p>Fill All Form Values</p>
    {/if}
</form>
