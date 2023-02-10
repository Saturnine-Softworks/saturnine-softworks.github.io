<script lang="ts">
    import IntersectionObserver from 'svelte-intersection-observer';
    import { fly } from "svelte/transition";
    const mobile = screen.width < 600;
    let node: HTMLElement;
</script>
<style>
    div {
        margin: auto;
        width: 100vw;
    }
</style>
{#if !mobile}
     <IntersectionObserver element={node} let:intersecting>
        <div bind:this={node}>
            {#if intersecting}
            <div in:fly={{ delay: 200, duration: 666, x: 600 }}>
                <slot/>
            </div>
            {/if}
        </div>
    </IntersectionObserver>
{:else}
<!-- Mobile devices can't use the intersection observer properly -->
    <div>
        <slot/>
    </div>
{/if}
