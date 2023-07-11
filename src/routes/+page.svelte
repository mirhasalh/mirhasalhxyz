<script lang="ts">
	import { AppBar, LightSwitch, Drawer, drawerStore } from '@skeletonlabs/skeleton';
	import type { DrawerSettings } from '@skeletonlabs/skeleton';
	import Menu from 'svelte-material-icons/Menu.svelte';
	import Github from 'svelte-material-icons/Github.svelte';
	import Linkedin from 'svelte-material-icons/Linkedin.svelte';
	import Instagram from 'svelte-material-icons/Instagram.svelte';
	import Android from 'svelte-material-icons/Android.svelte';

	let href = 'https://github.com/mirhasalh/mirhasalhxyz';
	let size = '1.5rem';
	let viewBox = '0 0 24 24';

	const drawerSettings: DrawerSettings = {
		id: 'main-drawer',
		width: 'w-auto'
	};
</script>

<Drawer>
	{#if $drawerStore.id === 'main-drawer'}
		<a href="https://flutter.mirhasalh.xyz/#/" class="btn variant-filled m-4" data-sveltekit-preload-data="hover" target="_blank">
			<Android {size} {viewBox} />
		</a>
		<br>
		<a {href} class="btn variant-filled m-4" data-sveltekit-preload-data="hover" target="_blank">
			<Github {size} {viewBox} />
		</a>
		<br>
		<a href="https://www.instagram.com/irhasdev/" class="btn variant-filled m-4" data-sveltekit-preload-data="hover" target="_blank">
			<Instagram {size} {viewBox} />
		</a>
		<br>
		<a href="https://www.linkedin.com/in/irhas-a-914681230" class="btn variant-filled m-4" data-sveltekit-preload-data="hover" target="_blank">
			<Linkedin {size} {viewBox} />
		</a>
	{:else}
		<div>...</div>
	{/if}
</Drawer>
<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
	<svelte:fragment slot="lead">
		<button
			type="button"
			class="btn-icon bg-initial"
			on:click={() => drawerStore.open(drawerSettings)}
		>
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
