<script lang="ts">
	import { AppBar, LightSwitch, Drawer, drawerStore } from '@skeletonlabs/skeleton';
	import type { DrawerSettings } from '@skeletonlabs/skeleton';
	import Menu from 'svelte-material-icons/Menu.svelte';
	import Github from 'svelte-material-icons/Github.svelte';
	import Linkedin from 'svelte-material-icons/Linkedin.svelte';
	import Instagram from 'svelte-material-icons/Instagram.svelte';

	let size = '1.5rem';
	let viewBox = '0 0 24 24';

	const drawerSettings: DrawerSettings = {
		id: 'main-drawer',
		width: 'w-auto'
	};
</script>

<Drawer>
	{#if $drawerStore.id === 'main-drawer'}
		<br>
		<button class="btn variant-filled mx-4 my-2" data-sveltekit-preload-data="hover" on:click={() => window.open('https://github.com/mirhasalh', '_blank')}>
			<span><Github {size} {viewBox} /></span>
		</button>
		<br>	
		<button class="btn variant-filled mx-4 my-2" data-sveltekit-preload-data="hover" on:click={() => window.open('https://www.instagram.com/irhasdev/', '_blank')}>
			<span><Instagram {size} {viewBox} /></span>
		</button>
		<br>
		<button class="btn variant-filled mx-4 my-2" data-sveltekit-preload-data="hover" on:click={() => window.open('https://www.linkedin.com/in/irhas-a-914681230', '_blank')}>
			<span><Linkedin {size} {viewBox} /></span>
		</button>
	{:else}
		<div/>
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
	<button class="btn-icon bg-initial" data-sveltekit-preload-data="hover" on:click={() => window.open('https://github.com/mirhasalh/mirhasalhxyz', '_blank')}>
		<span><Github {size} {viewBox} /></span>
	</button>
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
