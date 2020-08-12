<script>
	import {toast} from "svelte-toastify";
	import Code from "../components/Code.svelte";
	import PageHeader from "../components/PageHeader.svelte";

	const onClickHandler = (e) => {
		toast.success("This is a success toast.");
	}
	const importStr = `import {toast, ToastContainer} from "svelte-toastify";`;
	const HTMLmarkup = `<main><ToastContainer></main>`;
	const fireToast = `toast.success("This is a sucess toast.");`;
	const onMountImport = `import { onMount } from 'svelte';`
	const toastCompnent = `let ToastComponent;`;
	const importToast = `import { toast } from 'svelte-toastify'`
	const onMount = `
		onMount(async () => {
			const module = await import('svelte-toastify');
			ToastComponent = module.ToastContainer;
		});
	`;
	const component = `<svelte:component this={ToastComponent}/>`;
</script>

<style>
.page__container {
	max-width: 1200px;
	margin: 0 auto;
	padding: 15px 15px;
	border-bottom: 1px solid #eee;
}

.row {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
	}
.col {
	flex: 1;
	height: auto
}

p {
	padding-right: 5px;
}
</style>

<svelte:head>
	<title>Get Started</title>
</svelte:head>
<PageHeader heading="Add svelte-toastify to an existing project." subheading="Installation depends of wether on the type of the project i.e. Svelte or Sapper."/>
<div class="page">
	<section class="page__container">
		<p>Library exports a class <strong>toast</strong> and a component <strong>ToastContainer</strong>.
			toast class is used to configure and fire toasts from anywhere inside the appilcation
			ToastContainer component is used to display the toasts.
		</p>
	</section>
	<section class="page__container">
		<h2>Svelte Project</h2>
		<div class="row">
			<div class="col">
				<h3>1. Install</h3>
				<p>Svelte project is clent rendered, install as a dependency.</p>
			</div>
			<div class="col">
				<Code syntax="npm install svelte-toastify --save"/>
			</div>
		</div>
		<div class="row">
			<div class="col">
				<h3>2. Initialize</h3>
					
				<p>import in App.svelte and append the ToastContainer</p>
			</div>
			<div class="col">
				<Code syntax={importStr}/>
				<Code syntax={HTMLmarkup}/>
			</div>
		</div>
		<div class="row">
			<div class="col">
				<h3>3. Fire A Toast</h3>
				<p>Use toast class to fire toast notification, by default toasts will appear on the bottom right.</p>	
				Click here to see basic success toast. <button on:click={onClickHandler}>Success</button>
				<p>Now that we have the toast up and running check out what it can do in API section</p>
			</div>
			<div class="col">
				<Code syntax={fireToast}/>
			</div>
		</div>
			
		
		
	</section>
	<section class="page__container">
		<h2>Sapper Project</h2>
		<div class="row">
			<div class="col">
				<h3>1. Install</h3>
				<p>Svelte project is server side rendered, install as a dev dependency.</p>
			</div>
			<div class="col">
				<Code syntax="npm install -D svelte-toastify"/>
			</div>
		</div>
		<div class="row">
			<div class="col">
				<h3>2. Initialize</h3>
				<p> Sapper does a near-perfect job of supporting third-party modules, 
					there are some that require access to the window object, and as 
					you know, you can’t access window from the server side. 
					Simply importing such a module will cause your compile to fail, 
					and the world will become a bit dimmer. Hence the following workaround.</p>
				<p>import onMount from svelte in <strong>_layout.svelte</strong> file.</p>
				<p>Dynamically import svelte-toastify and assign the ToastContainer to some variable</p>
				<p>Append the component.</p>
			</div>
			<div class="col">
				<Code syntax={onMountImport}/>
				<Code syntax={toastCompnent}/>
				<Code syntax={onMount}/>
				<Code syntax={component}/>
			</div>
			
		</div>
		<div class="row">
			<div class="col">
				<h3>3. Fire A Toast</h3>
				<p>import toast from svelte-toastify on any page in your sapper app</p>	
				<p>Use toast class to fire toast notification, by default toasts will appear on the bottom right.</p>
				Click here to see basic success toast. <button on:click={onClickHandler}>Success</button>
				<p>Now that we have the toast up and running check out what it can do in API section</p>
			</div>
			<div class="col">
				<Code syntax={importToast}/>
				<Code syntax={fireToast}/>
			</div>
		</div>
	</section>
</div>
