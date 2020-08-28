<script>
    import Sidebar from "../../components/Sidebar.svelte";
    import Code from "../../components/Code.svelte";

    const SNIPPETS = {
        customId: `
            toast.success(
                "This is a success toast with id 121.",
                { toastId: "121" }
            );
        `,
    };
</script>

<svelte:head>
    <title>Custom ID</title>
</svelte:head>
<div class="usages-page">
    <Sidebar />
    <section class="usages-page__container">
        <div class="usages-content">
            <h1>Use a custom id</h1>
            <p>
                by default each toast is assigned a unique id, you can pass a
                custom id to replace it.
            </p>
            <Code syntax={SNIPPETS.customId} />
        </div>
    </section>
</div>
