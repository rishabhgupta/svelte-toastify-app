<script>
    import Sidebar from "../../components/Sidebar.svelte";
    import Code from "../../components/Code.svelte";
    import { toast } from "svelte-toastify";

    const SNIPPETS = {
        id: `
            const id = toast.success("This is a toast.");
        `,
        remove: `
            toast.delete(id);
        `,
    };

    let toastId;

    const fireToast = () => {
        toastId = toast.success(
            "This is a toast which will not get removed untill the user clicks on the cross icon",
            {
                autoClose: false,
            }
        );
    };

    const deleteToast = () => {
        toast.delete(toastId);
    };
</script>

<svelte:head>
    <title>Delete Toast</title>
</svelte:head>
<div class="usages-page">
    <Sidebar />
    <section class="usages-page__container">
        <div class="usages-content">
            <h1>Remove toast programatically</h1>
            <p>
                every toast call returns a toast id. If custom toast id is
                passed via
                <code>toastId</code>
                option then that will be retuned, else generated id is retuned.
            </p>
            <Code syntax={SNIPPETS.id} />
            <p>
                You can use this save this id and use it to programatically
                remove a toast.
            </p>
            <Code syntax={SNIPPETS.remove} />
            <button class="secondary" on:click={fireToast}>
                Fire a Toast!
            </button>
            <button class="secondary" on:click={deleteToast}>
                Delete the Toast!
            </button>
        </div>
    </section>
</div>
