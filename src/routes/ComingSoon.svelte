<script>
    export let show = true;
    export let text = "Coming Soon";
</script>

{#if show}
    <div class="overlay">
        <div class="content">
            {text}
        </div>
    </div>
{/if}

<style>
    .overlay {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgb(255 255 255 / 20%);
        backdrop-filter: blur(5px);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1000;
    }

    .content {
        font-size: 2rem;
        font-weight: bold;
        color: #fff;
        text-align: center;
        border-radius: 8px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }
</style>