<script lang="ts">
    import { twMerge } from "tailwind-merge";
    import { inertia } from "@inertiajs/svelte";
    import {
        buttonVariants,
        type ButtonVariant,
        type ButtonSize,
    } from "@/Components/ui/button";
    import Button from "@/Components/ui/button/button.svelte";

    interface Props {
        link?: boolean;
        method?: string;
        variant?: ButtonVariant;
        size?: ButtonSize;
        class?: string;
        children?: import('svelte').Snippet;
        [key: string]: any
    }

    let {
        link = false,
        method = "get",
        variant = "default",
        size = "default",
        class: className = "",
        children,
        ...rest
    }: Props = $props();
</script>

{#if link}
    <!-- svelte-ignore a11y_missing_attribute -->
    <a
        use:inertia={{ method }}
        class={twMerge(
            buttonVariants({ variant, size }),
            "font-medium tracking-wide",
            className,
        )}
        {...rest}
    >
        {@render children?.()}
    </a>
{:else}
    <Button
        class={twMerge("font-medium tracking-wide", className)}
        {variant}
        {size}
        {...rest}
        on:click
    >
        {@render children?.()}
    </Button>
{/if}
