<script>
    export let syntax;

    const lines = syntax.split("|");
</script>

<style>
    .code {
        overflow: auto;
        padding: 1.5rem 2rem;
        margin: 0.8em 0em;
        /* max-width: var(--code-w); */
        background-color: aliceblue;
        border-radius: var(--border-r);
        font-family: monospace;
        color: #666;
        box-shadow: 1px 1px 1px rgba(68, 68, 68, 0.12) inset;
    }

    p {
        margin: 0;
        padding: 0;
    }
</style>

<div class="code">
    {#each lines as line}
        <p>{line}</p>
    {/each}
</div>
