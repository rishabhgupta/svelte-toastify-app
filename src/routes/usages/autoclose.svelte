<script>
    import Sidebar from "../../components/Sidebar.svelte";
    import { toast } from "svelte-toastify";
    import Code from "../../components/Code.svelte";

    let timeValue = 3000;
    const handleTimeValueChange = (e) => {
        timeValue = e.target.value;
    };
    const hanldleOnClick = (e) => {
        if (e.target.name === "success") {
            toast.success("This is a success message", {
                autoClose: timeValue,
            });
        }

        if (e.target.name === "danger") {
            toast.error("This is an error message", { autoClose: timeValue });
        }

        if (e.target.name === "info") {
            toast.info("This is an info message", { autoClose: timeValue });
        }

        if (e.target.name === "warning") {
            toast.warning("This is an warning message", {
                autoClose: timeValue,
            });
        }
    };

    const SNIPPETS = {
        defaultDelay: `
            import { toast } from 'svelte-toastify';|
            toast.configure({autoClose: 1000});
        `,
        delayFifteen: `
            toast.success("This is a success toast which will auto close after 15 secs.", {autoClose: 15000};
        `,
        delayThree: `
            toast.error("This is a success toast which will auto close after 3 secs.", {autoClose: 3000};
        `,
        defaultPrevent: `
            import { toast } from 'svelte-toastify';|
            toast.configure({autoClose: false});
        `,
        preventToast: `
            toast.error("This is a error toast which will close only when user clicks on the close button", {autoClose: false};
        `,
    };

    const handleOnDelay = (e) => {
        toast.success(
            `This is a success toast which will auto close after ${e.target.name} milliseconds.`,
            { autoClose: parseInt(e.target.name, 10) }
        );
    };

    const handlePreventClose = () => {
        toast.error(
            `This is a error toast which will auto close only when user clicks on the close button`,
            { autoClose: false }
        );
    };
</script>

<style>
    h2 {
        margin-top: 15px;
    }
</style>

<svelte:head>
    <title>Auto Close</title>
</svelte:head>
<div class="usages-page">
    <Sidebar />
    <section class="usages-page__container">
        <div class="usages-content">
            <h1>Auto Close</h1>
            <p>
                The
                <code>autoClose</code>
                prop accept a duration in milliseconds or false. By default its
                set to 5000 ms.
            </p>
            <p>
                If set to false then toast will not dismiss unless the user
                closes them.
            </p>

            <h2>Change the defualt value</h2>
            <p>
                by setting autoClose in configuration options. Close all toasts
                after 10s instead of default 5s.
            </p>
            <Code syntax={SNIPPETS.defaultDelay} />

            <h2>Change the delay per toast for more control</h2>
            <p>
                by setting autoClose in additional options, this will override
                default value for the toast.
            </p>
            <p>Close a specfic toast after 15s.</p>
            <Code syntax={SNIPPETS.delayFifteen} />
            <button class="secondary" name="15000" on:click={handleOnDelay}>
                Hit ME!
            </button>
            <p>Close a specfic toast after 3s.</p>
            <Code syntax={SNIPPETS.delayThree} />
            <button class="secondary" name="3000" on:click={handleOnDelay}>
                Hit ME!
            </button>
            <br />
            <br />
            <hr />
            <h2>Try it out yourself</h2>
            <input
                label="time"
                value={timeValue}
                on:change={handleTimeValueChange} />
            <button class="secondary" name="success" on:click={hanldleOnClick}>
                Success
            </button>
            <button class="secondary" name="danger" on:click={hanldleOnClick}>
                Danger
            </button>
            <button class="secondary" name="info" on:click={hanldleOnClick}>
                Info
            </button>
            <button class="secondary" name="warning" on:click={hanldleOnClick}>
                Warning
            </button>
            <br />
            <br />
            <hr />
            <br />
            <h2>Prevent all toasts from auto closing.</h2>
            <p>by setting autoClose to false in the configuration</p>
            <Code syntax={SNIPPETS.defaultPrevent} />

            <h2>Prevent specific toasts from auto closing.</h2>
            <p>by setting autoClose to false in additional toast options.</p>
            <Code syntax={SNIPPETS.preventToast} />
            <button class="secondary" on:click={handlePreventClose}>
                Hit ME!
            </button>
        </div>

    </section>
</div>
