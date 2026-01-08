<script lang="ts">
    import type { Snippet } from "svelte";
    let { title, children } = $props<{ title?: string, children: Snippet }>();
</script>

<div class="legend-container">
    {#if title}
        <h4 class="legend-title">{title}</h4>
    {/if}
    <div class="legend-items">
        {@render children()}
    </div>
</div>

<style>
    .legend-container {
        position: relative;
        margin-top: 0.6rem;
    }
    .legend-title {
        margin: 0 0 0.5rem 0;
        font-size: 0.75rem;
        font-weight: bold;
        text-transform: uppercase;
        color: #666;
    }
    .legend-items {
        display: flex;
        flex-direction: column; 
        flex-direction: row; 
        flex-wrap: wrap; 
        gap: 1rem; 
    }
    @media (min-width: 768px) {
        .legend-container {
            position: relative;
            margin-top: 0.85rem;
        }
        .legend-title {
            font-size: 0.95rem;
            margin-bottom:0.5rem;
        }
    }
</style>