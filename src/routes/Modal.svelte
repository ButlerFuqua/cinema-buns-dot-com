<script>
    import { fade, blur, fly } from "svelte/transition";
    import { quintOut } from "svelte/easing";
    import Close from "./CloseIcon.svelte";

    export let isOpen = false;
    export let onClose;
</script>

{#if isOpen}
    <div
        class="modal-overlay"
        on:click={onClose}
        transition:blur={{ duration: 300, amount: 8 }}
    >
        <div
            class="modal-content"
            on:click|stopPropagation
            transition:fly={{ duration: 400, easing: quintOut, y: -50 }}
        >
            <button on:click={onClose}><Close /></button>
            <div>
                <slot />
            </div>
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
        background: var(--default-bg);
        padding: var(--default-padding);
        border-radius: 8px;
        width: 500px;
        max-width: 80%;
        max-height: 80%;
        overflow: auto;
        display: flex;
        flex-direction: column;
        box-shadow: 2px 3px 3px 4px var(--blue-color);
    }

    button {
        background: none;
        border: none;
    }
</style>
