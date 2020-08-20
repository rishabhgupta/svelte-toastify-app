<script>
    export let segment;
</script>

<style>
    nav {
        border-bottom: 1px solid rgba(255, 62, 0, 0.1);
        font-weight: 300;
        padding: 0 1em;
        display: flex;
    }

    ul {
        margin: 0;
        padding: 0;
        display: inline;
        float: right;
    }

    /* clearfix */
    ul::after {
        content: "";
        display: block;
        clear: both;
    }

    li {
        display: block;
        float: left;
    }

    [aria-current] {
        position: relative;
        display: inline-block;
    }

    [aria-current]::after {
        position: absolute;
        content: "";
        width: calc(100% - 1em);
        height: 2px;
        background-color: rgb(255, 62, 0);
        display: block;
        bottom: -1px;
    }

    a {
        text-decoration: none;
        padding: 1em 0.5em;
        display: block;
    }
    .logo {
        flex: 1;
        padding: 17px 10px;
    }
    .logo h3 {
        margin: 0px;
    }
</style>

<nav>
    <div class="logo">
        <h3>
            SVELTE
            <b>TOASTIFY</b>
        </h3>
    </div>
    <div style="flex:1">
        <ul>
            <li>
                <a
                    aria-current={segment === undefined ? 'page' : undefined}
                    href=".">
                    Home
                </a>
            </li>
            <li>
                <a
                    aria-current={segment === 'getstarted' ? 'page' : undefined}
                    href="getstarted">
                    Get Started
                </a>
            </li>

            <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
				the blog data when we hover over the link or tap it on a touchscreen -->
            <li>
                <a
                    rel="prefetch"
                    aria-current={segment === 'usages' ? 'page' : undefined}
                    href="usages">
                    Usages
                </a>
            </li>
            <li>
                <a
                    rel="prefetch"
                    aria-current={segment === 'api' ? 'page' : undefined}
                    href="api">
                    API
                </a>
            </li>
            <li>
                <a
                    rel="prefetch"
                    aria-current={segment === 'api' ? 'page' : undefined}
                    href="api">
                    Github
                </a>
            </li>
            <li>
                <a
                    rel="prefetch"
                    aria-current={segment === 'blog' ? 'blog' : undefined}
                    href="blog">
                    blog
                </a>
            </li>
        </ul>
    </div>
</nav>
