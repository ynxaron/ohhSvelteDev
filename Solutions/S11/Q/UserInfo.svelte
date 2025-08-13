<script>
    let {isAdmin} = $props();
</script>

{#if isAdmin}
    <p>Admin Access</p>
{:else}
    <p>User Access</p>
{/if}
