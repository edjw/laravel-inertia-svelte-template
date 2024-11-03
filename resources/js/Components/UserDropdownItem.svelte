<script lang="ts">
    import { inertia, page } from "@inertiajs/svelte";
    import * as DropdownMenu from "@/Components/ui/dropdown-menu";

    interface Props {
        href: string;
        method?: string;
        children?: import('svelte').Snippet;
    }

    let { href, method = "get", children }: Props = $props();
</script>

<DropdownMenu.Item asChild>
    <a
        {href}
        class="block px-2 py-2 rounded hover:bg-muted"
        class:active={$page.url === href}
        use:inertia={{ method }}
    >
        {@render children?.()}
    </a>
</DropdownMenu.Item>

<style lang="postcss">
    .active {
        @apply bg-primary/5;
    }
</style>
