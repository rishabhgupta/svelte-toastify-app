<script>
	import {toast} from "svelte-toastify";
	import PageHeader from "../components/PageHeader.svelte";
	import CustomToast from "../components/CustomToast.svelte";


	const onBasicHandler = (e) => {
		toast.success("This is a basic success toast, with zero configuration.");
	}

	const onCustomHandler = (e) => {
		toast.warning("This is custom toast with on the fly configuration.", {
			icon: true,
			title: "Configure Me",
		})
	}

	const onComponentHandler =() => {
		toast.error(CustomToast, {
			color: "#f1f1f1",
			closeButton:  false,
		});
	}



</script>
<style>
	h1, p {
		margin: 0 auto;
	}

	

	p {
		margin: 1em auto;
	}

	.page {
		width: 100%;
	}

	.page__container {
		max-width: 1200px;
		margin: 0 auto;
	}

	.row {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
	}
	.col {
		margin-top: 25px;
		flex: 1 1 350px;
		height: 230px;
	}
	.card {
		width:80%;
		height: 85%;
		margin: 0 auto;
		border-radius: 5px;
		padding: 15px 25px;
		color: white;
	}
</style>

<svelte:head>
	<title>Svelte Toastify</title>
</svelte:head>



<div class="page">
	<PageHeader heading="SVELTE TOASTIFY" subheading="Configurable, easy to use toast library for svelte apps."/>
	<section class="page__container">
		<div class="row" style="margin-top: -100px;">
			<div class="col">
				<div class="card" style="background-color: #5cb85c;">
					<h2>Easy to <b>Set Up</b></h2>
					<p>Add toast notifications to you svelte/sapper apps in seconds. Checkout the getting started section for more details.</p>
					Checkout the basic toast. <button on:click={onBasicHandler}>Hit Me</button>
				</div>
			</div>
			<div class="col" style="">
				<div class="card" style="background-color: #f0ad4e">
					<h2>Make it <b>Your Own</b></h2>
					<p>Customize where to show the toast with various Positions, change the look by passing classNames, add icon and more.</p>
					Checkout a custom toast. <button on:click={onCustomHandler}>Hit Me</button>
				</div>
			</div>
			<div class="col">
				<div class="card" style="background-color: #d9534f">
					<h2>More than <b>Strings</b></h2>
					<p>Pass custom svelte component instead of string for content and close button. Control the visibilty of the toast.</p>
					Checkout a component as a toast. <button on:click={onComponentHandler}>Hit Me</button>
				</div>
			</div>
		</div>
	</section>
	<br/>
	<section class="page__container">
		<div class="row" style="padding: 0px 15px;">
			<div style="flex:2;padding-right:20px;">
				<p>Sapper is a framework for building web applications of all sizes, with a beautiful development experience and flexible filesystem-based routing.

Unlike single-page apps, </p><p>Sapper doesn't compromise on SEO, progressive enhancement or the initial load experience — but unlike traditional server-rendered apps, navigation is instantaneous for that app-like feel.

 to learn more.</p>
			</div>
			<div style="flex:1">
				<div style=" overflow: auto;
    padding: 1.5rem 2rem;
    margin: .8rem 0 2.4rem;
    /* max-width: var(--code-w); */
	border-radius: var(--border-r);
	font-family: monospace;
	color: #666;
	box-shadow: 1px 1px 1px rgba(68, 68, 68, .12) inset;"> 
					#svelte
					<br>
					npm install svelte-toastify
					<br>
					<br>
					#sapper
					<br>
					npm install -D svelte-toastify
				</div>
				<button>Know More</button>
			</div>
		</div>
	</section>
</div>
	<br/>
<section class="page__container">
	<div class="row" style="padding: 0px 15px;">
		footer
	</div>
</section>
		