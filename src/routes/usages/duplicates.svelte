<script>
    import Sidebar from "../../components/Sidebar.svelte";
    import Code from "../../components/Code.svelte";
    import { toast } from "svelte-toastify";

    toast.configure({
        preventDuplicate: true,
    });

    const SNIPPETS = {
        defaultDuplicate: `
            import { toast } from 'svelte-toastify';
            toast.configure({preventDuplicate: true});
        `,
        toastId: `
            toast.success("This is a success toast with id 121, as long as I am showing no other toast with same id will be shown.", {toastId: "121"});
        `,
    };

    const handleDuplicates = () => {
        toast.success(
            "This is a success toast with id 121, as long as I am showing no other toast with same id will be shown.",
            { toastId: "121" }
        );
    };
</script>

<svelte:head>
    <title>Prevent Duplicates</title>
</svelte:head>
<div class="usages-page">
    <Sidebar />
    <section class="usages-page__container">
        <div class="usages-content">
            <h1>Prevent Duplicates</h1>
            <p>
                The
                <code>preventDuplicate</code>
                option in configuation object is false by default, set this is
                true to prevent duplicate toasts.
            </p>
            <Code syntax={SNIPPETS.defaultDuplicate} />
            <br />
            <h2>Add toastId to each toast</h2>
            <p>
                For each toast pass a
                <code>toastId</code>
                in additional options, this id will be used to prevent toasts of
                the same id showing on the screen.
            </p>
            <Code syntax={SNIPPETS.toastId} />
            <button class="secondary" on:click={handleDuplicates}>
                Hit ME!
            </button>
            <span>
                &nbsp;
                <i>Click multiple times to generate duplicates</i>
            </span>
        </div>
    </section>
</div>
