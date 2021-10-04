<script>
    export let type = "button";
    export let link = "/"
    export let className
    className = className + " text-white bg-indigo-500 border-0 py-2 px-8 focus:outline-none hover:bg-indigo-600 rounded text-lg btn"
</script>

<div>
    {#if type === "button"}
        <button
            class={className}
            type="button">
            <slot/>
        </button>
    {:else if type === "link"}
        <a
            class={className}
            href={link}>
            <slot/>
        </a>
    {/if}
</div>


<style>
    .btn {
        transform: scale(1);
    }
    .btn:active {
        transform: scale(1.02);
    }
</style>