<script>
    import Nav from "../components/Nav.svelte";
    import { toast } from "svelte-toastify";

    export let segment;

    import { onMount } from "svelte";

    let ToastComponent;

    toast.configure({
        position: "bottom-right",
    });

    onMount(async () => {
        const module = await import("svelte-toastify");
        ToastComponent = module.ToastContainer;
    });
</script>

<style>
    main {
        position: relative;
        max-width: 100%;
        background-color: white;
        margin: 0 auto;
        box-sizing: border-box;
    }
</style>

<Nav {segment} />

<main>
    <slot />
</main>
<svelte:component this={ToastComponent} />
