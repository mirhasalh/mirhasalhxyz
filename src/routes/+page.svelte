<script>
	import { AppBar } from '@skeletonlabs/skeleton';
	import { LightSwitch } from '@skeletonlabs/skeleton';
	import { Drawer, drawerStore } from '@skeletonlabs/skeleton';
	import Menu from 'svelte-material-icons/Menu.svelte';
	import Github from 'svelte-material-icons/Github.svelte';

	let href = 'https://github.com/mirhasalh/mirhasalhxyz';
	let size = '1.5rem';
	let viewBox = '0 0 24 24';
</script>

<Drawer />
<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
	<svelte:fragment slot="lead">
		<button type="button" class="btn-icon bg-initial" on:click={() => drawerStore.open()}>
			<Menu {size} {viewBox} />
		</button>
	</svelte:fragment>
	<a {href} target="_blank" type="button" class="btn-icon bg-initial">
		<Github {size} {viewBox} />
	</a>
	<svelte:fragment slot="trail">
		<LightSwitch />
	</svelte:fragment>
</AppBar>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<h1 class="h1">Let's get cracking bones!</h1>
		<p>Start by exploring:</p>
		<ul>
			<li><code class="code">/src/routes/+layout.svelte</code> - barebones layout, the CSS import order is critical!</li>
			<li><code class="code">/src/app.postcss</code> - minimal css to make the page full screen, may not be relevant for your project</li>
			<li><code class="code">/src/routes/+page.svelte</code> - this page, you can replace the contents</li>
		</ul>
	</div>
</div>
