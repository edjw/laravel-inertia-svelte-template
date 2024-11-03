<script lang="ts">
    interface Props {
        children?: import('svelte').Snippet;
    }

    let { children }: Props = $props();
</script>

<div class="flex flex-col mb-6 gap-y-2">
    {@render children?.()}
</div>
