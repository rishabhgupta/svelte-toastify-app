<script>
    import Sidebar from "../../components/Sidebar.svelte";
</script>

<svelte:head>
    <title>Positioning</title>
</svelte:head>
<div class="usages-page">
    <Sidebar />
    <section class="usages-page__container">
        <div class="usages-content">
            <h1>Positioning</h1>
            <!-- svelte-ignore a11y-no-onchange -->
            By default, all the toasts will be positioned on the top right of
            your browser. If a position is set on a toast, the one defined on
            ToastContainer will be replaced. The following values are allowed:
            top-right, top-center, top-left, bottom-right, bottom-center,
            bottom-left For convenience, toast exposes a POSITION property to
            avoid any typos.
        </div>
    </section>
</div>
