<script lang="ts">
    import IntersectionObserver from 'svelte-intersection-observer';
    import { fly } from "svelte/transition";
    let node: HTMLElement;
</script>
<style>
    div {
        margin: auto;
        width: 100vw;
    }
</style>
<IntersectionObserver element={node} let:intersecting>
    <div bind:this={node}>
        {#if intersecting}
            <div in:fly={{ delay: 200, duration: 666, x: 600 }}>
                <slot/>
            </div>
        {/if}
    </div>
</IntersectionObserver>
