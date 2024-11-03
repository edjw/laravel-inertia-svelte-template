<script>
    import { page, inertia } from "@inertiajs/svelte";

    let { href, children } = $props();

    let active = $derived($page.url === href);
</script>

<a
    {href}
    use:inertia
    class:active
    class="inline-flex items-center px-2 py-3 text-sm font-medium leading-4 transition border-b-2 border-transparent text-muted-foreground hover:border-gray-200"
>
    {@render children?.()}
</a>

<style lang="postcss">
    .active {
        @apply border-primary border-b-2 text-gray-900;
    }
</style>
