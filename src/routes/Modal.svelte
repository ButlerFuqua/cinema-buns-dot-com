<script>
    export let isOpen = false;
    export let onClose;
</script>

{#if isOpen}
    <div class="modal-overlay" on:click={onClose}>
        <div class="modal-content" on:click|stopPropagation>
            <button on:click={onClose}>Close</button>
            <slot />
        </div>
    </div>
{/if}

<style>
    .modal-overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.6);
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 1000;
        backdrop-filter: blur(5px);
        -webkit-backdrop-filter: blur(5px); /* Safari support */
    }

    .modal-content {
        background: white;
        padding: 20px;
        border-radius: 8px;
        max-width: 90%;
        max-height: 90%;
        overflow: auto;
    }
</style>
