<script>
    export let syntax;
</script>

<style>
    .code {
        overflow: auto;
        padding: 1.5rem 2rem;
        margin: .8rem 0 2.4rem;
        /* max-width: var(--code-w); */
        background-color: aliceblue;
        border-radius: var(--border-r);
        font-family: monospace;
        color: #666;
        box-shadow: 1px 1px 1px rgba(68, 68, 68, .12) inset;
    }

</style>

<div class="code"> 
    {syntax}
</div>