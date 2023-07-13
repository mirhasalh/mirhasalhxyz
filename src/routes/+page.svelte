<script lang="ts">
	import { AppBar, LightSwitch, Drawer, drawerStore, AppRail, AppRailAnchor } from '@skeletonlabs/skeleton';
	import type { DrawerSettings } from '@skeletonlabs/skeleton';
	import Menu from 'svelte-material-icons/Menu.svelte';
	import Github from 'svelte-material-icons/Github.svelte';
	import Linkedin from 'svelte-material-icons/Linkedin.svelte';
	import Instagram from 'svelte-material-icons/Instagram.svelte';

	let size = '1.5rem';
	let viewBox = '0 0 24 24';
	let innerWidth = 0;

	const drawerSettings: DrawerSettings = {
		id: 'main-drawer',
		width: 'w-auto'
	};
</script>

<svelte:window bind:innerWidth />

<Drawer>
	{#if $drawerStore.id === 'main-drawer'}
		<br>
		<button class="btn variant-filled mx-4 my-2" data-sveltekit-preload-data="hover" on:click={() => window.open('https://flutter.mirhasalh.xyz/', '_blank')}>
			<span class="material-symbols-outlined">flutter</span>
		</button>
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

{#if innerWidth > 640}
	<AppRail class="fixed z-10">
	<AppRailAnchor href="https://flutter.mirhasalh.xyz/" target="_blank" title="Flutter">
		<svelte:fragment slot="lead">
			<span class="material-symbols-outlined">flutter</span>
		</svelte:fragment>
		<span>Flutter</span>
	</AppRailAnchor>
	<AppRailAnchor href="https://github.com/mirhasalh" target="_blank" title="GitHub">
		<svelte:fragment slot="lead">
			<Github {size} {viewBox} />
		</svelte:fragment>
		<span>GitHub</span>
	</AppRailAnchor>
	<AppRailAnchor href="https://www.instagram.com/irhasdev/" target="_blank" title="Instagram">
		<svelte:fragment slot="lead">
			<span><Instagram {size} {viewBox} /></span>
		</svelte:fragment>
		<span>Instagram</span>
	</AppRailAnchor>
	<AppRailAnchor href="https://www.linkedin.com/in/irhas-a-914681230" target="_blank" title="Linkedin">
		<svelte:fragment slot="lead">
			<span><Linkedin {size} {viewBox} /></span>
		</svelte:fragment>
		<span>Linkedin</span>
	</AppRailAnchor>
	<svelte:fragment slot="trail">
		<AppRailAnchor href="/" title="Light Switch">
			<svelte:fragment slot="lead"><LightSwitch /></svelte:fragment>
		</AppRailAnchor>
	</svelte:fragment>
	</AppRail>
{/if}

{#if innerWidth <= 640}
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
{/if}

<div class="container" style={`${innerWidth > 640 ? "padding-left: 88px;" : ""}`}>
	<div class="p-8 space-y-5">
		<h1 class="h1">Let's get cracking bones!</h1>
		<p>Start by exploring:</p>
		<ul>
			<li><code class="code">/src/routes/+layout.svelte</code> - barebones layout, the CSS import order is critical!</li>
			<li><code class="code">/src/app.postcss</code> - minimal css to make the page full screen, may not be relevant for your project</li>
			<li><code class="code">/src/routes/+page.svelte</code> - this page, you can replace the contents</li>
		</ul>
	</div>
</div>

<svelte:head>
	<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />
</svelte:head>

<style>
	.material-symbols-outlined {
	  font-variation-settings:
	  'FILL' 0,
	  'wght' 400,
	  'GRAD' 0,
	  'opsz' 48
	}
</style>