<script>
    export let heading;
    export let subheading;
</script>


<style>
    .page__master-header {
            height: 500px;
            background-color: #313d47;
            color: white;
    }

    .page__master-header__container {
        max-width: 1200px;
        margin: 0 auto;
    }
    h1 {
        font-size: 2.8em;
        font-weight: 600;
        margin-bottom: 5px;
    }


    img {
        width: 100%;
        max-width: 400px;
    }
</style>

<section class="page__master-header">
    <div class="page__master-header__container">
        <div style="display: flex">
            <div style="flex:1; padding-left:10px;">
                <h1 style="margin-top:20%; font-size: 3.4em;">{heading}</h1>
                <h3>{subheading}</h3>
            </div>
            <img src="svelte-logo-outline.svg" alt="logo"/>
        </div>
    </div>
</section>