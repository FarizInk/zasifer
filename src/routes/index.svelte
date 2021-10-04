<script>
    import Input from "../components/Input.svelte";
    import Button from "../components/Button.svelte";

    let email = ""
    let pass = ""
</script>

<svelte:head>
    <title>ZASIFER</title>
</svelte:head>

<div class="flex justify-center items-center min-h-screen dark:text-gray-400 dark:bg-gray-900">
    <div class="lg:w-2/6 md:w-1/2 bg-gray-100 dark:bg-gray-800 dark:bg-opacity-50 rounded-lg p-8 flex flex-col shadow-lg">
        <h2 class="text-gray-900 dark:text-white text-xl font-bold title-font mb-3">Sign In</h2>
        <div class="relative mb-4">
            <label for="email" class="leading-7 text-sm text-gray-600 dark:text-gray-400">Email</label>
            <Input type="email" placeholder="Email" id="email" bind:value={email}/>
        </div>
        <div class="relative mb-4">
            <label for="password" class="leading-7 text-sm text-gray-600 dark:text-gray-400">Password</label>
            <Input type="password" placeholder="Password" id="password" bind:value={pass} />
        </div>
        <Button className="w-full">
            Login
        </Button>
    </div>
</div>
