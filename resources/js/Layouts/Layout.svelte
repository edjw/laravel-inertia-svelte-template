<script lang="ts">
    import NavBar from "@/Components/NavBar.svelte";
    import { twMerge } from "tailwind-merge";


    interface Props {
        gray?: boolean;
        class?: string;
        children?: import('svelte').Snippet;
    }

    let { gray = false, class: className = "", children }: Props = $props();
</script>

<NavBar />
<div class:gray class="pb-20">
    <div class={twMerge("px-4 mx-auto max-w-7xl sm:px-8", className)}>
        {@render children?.()}
    </div>
</div>

<style lang="postcss">
    .gray {
        min-height: calc(100dvh - 65px);
        @apply bg-slate-100;
    }
</style>
