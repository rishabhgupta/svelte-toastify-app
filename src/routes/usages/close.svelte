<script>
    import Sidebar from "../../components/Sidebar.svelte";
    import Code from "../../components/Code.svelte";
    import CloseButton from "../../components/CloseButton.svelte";
    import { toast } from "svelte-toastify";

    const SNIPPETS = {
        default: `
            import { toast } from 'svelte-toastify';|
            toast.configure({closeButton: false});|
        `,
        remove: `
            toast.success("This is a toast with no close button.", {closeButton: false});|
        `,
        custom: `
            import CloseButton from 'svelte-toastify';|
            toast.success("This is a toast with no close button.", {closeButton: CloseButton});|
        `,
    };

    const handleOnClick = () => {
        toast.success("This is a toast with no close button.", {
            closeButton: false,
        });
    };

    const handleCustomClick = () => {
        toast.success("This is a toast with custom close button.", {
            closeButton: CloseButton,
        });
    };
</script>

<svelte:head>
    <title>Custom close button</title>
</svelte:head>
<div class="usages-page">
    <Sidebar />
    <section class="usages-page__container">
        <div class="usages-content">
            <h1>Use a custom close button or remove it</h1>
            <p>
                You can set a custom close button in default config using
                <code>closeButton</code>
                .
            </p>
            <h2>Remove close button from all toasts</h2>
            <p>
                set
                <code>closeButton</code>
                to false in configuration object
            </p>
            <Code syntax={SNIPPETS.default} />
            <h2>Remove close button for a specific toasts</h2>
            <p>
                set
                <code>closeButton</code>
                to false in additional options.
            </p>
            <Code syntax={SNIPPETS.remove} />
            <button class="secondary" on:click={handleOnClick}>Hit ME!</button>
            <br />
            <br />
            <br />
            <h2>Set a custom close button</h2>
            <p>
                set
                <code>closeButton</code>
                to svelte component in additional options for each toast or in
                the configuration object.
            </p>
            <Code syntax={SNIPPETS.custom} />
            <button class="secondary" on:click={handleCustomClick}>
                Hit ME!
            </button>
        </div>
    </section>
</div>
