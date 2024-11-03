<script>
    let { error } = $props();
</script>

{#if error}
    <p class="text-sm text-destructive">{error}</p>
{/if}
