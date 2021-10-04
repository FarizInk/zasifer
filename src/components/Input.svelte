<script>
    export let type = "text";
    export let placeholder;
    export let autoComplete = "off";
    export let value = '';
    export let id;
    export let className;
    export let errorMsg;
    export let successMsg;
    const realType = type;
    let showPassword = false;

    className = className + " w-full dark:focus:bg-transparent bg-white dark:bg-gray-600 dark:bg-opacity-20 rounded border border-gray-300 dark:border-gray-600 focus:border-indigo-500 focus:ring-2 focus:ring-indigo-200 dark:focus:ring-indigo-900 text-base outline-none text-gray-700 dark:text-gray-100 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out"
    if (realType === 'password') className = className + " pr-11"

    function toggleEye() {
        (type === 'password') ? type = 'text' : type = 'password'
	}
</script>

<div>
    <div class="relative">
        <input
            id={id}
            type={type}
            placeholder={placeholder}
            autocomplete={autoComplete}
            on:input={e => value = e.target.value}
            class={className}>
        {#if realType === 'password'}
            <button class="absolute inset-y-2 px-2 right-1.5 flex items-center focus:outline-none focus:ring-0 border-none dark:text-gray-300" on:click={toggleEye}>
                {#if type === 'password'}
                    <i class="ci-show text-2xl cursor-pointer"></i>
                {:else}
                    <i class="ci-hide text-2xl cursor-pointer"></i>
                {/if}
            </button>
        {/if}
    </div>
    {#if errorMsg !== undefined && errorMsg !== null && errorMsg !== ''}
        <div class="text-red-600 flex items-center gap-1 mt-2 mb-1">
            <i class="ci-error text-xl"></i> {errorMsg}
        </div>
    {/if}
    {#if successMsg !== undefined && successMsg !== null && successMsg !== ''}
        <div class="text-green-600 flex items-center gap-1 mt-2 mb-1">
            <i class="ci-circle_check text-xl"></i> {successMsg}
        </div>
    {/if}
</div>
