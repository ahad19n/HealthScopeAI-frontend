<script>
    export let text = "";
    export let isLoading = false;
    export let onClick = () => {};

    async function handleClick(event) {
        if (isLoading) return;
        await onClick(event);
    }
</script>

<style>
    button {
        width: 82%;
        height: 50px;
        font-size: 20px;
        font-weight: bold;
        color: white;
        background-color: #4A1578;
        border-radius: 10px;
        padding-left: 15px;
        padding-right: 15px;
        margin-bottom: 15px;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: opacity 0.2s;
    }
    button:hover {
        border: 2px solid white;
    }
    div {
        width: 0.8rem;
        height: 0.8rem;
        margin-left: 10px;
        border-radius: 50%;
        border: 2px solid transparent;
        border-top: 2px solid white;
        animation: spin 0.6s linear infinite;
    }
    @keyframes spin {
        from { transform: rotate(0deg); }
        to   { transform: rotate(360deg); }
    }
</style>

<button on:click={handleClick}><span>{text}</span>
    {#if isLoading} <div></div> {/if}
</button>
