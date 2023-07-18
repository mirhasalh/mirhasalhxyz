<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { AppBar, LightSwitch, Drawer, drawerStore, AppRail, AppRailAnchor, AppShell } from '@skeletonlabs/skeleton';
	import Home from 'svelte-material-icons/Home.svelte';
	import Github from 'svelte-material-icons/Github.svelte';
	import Menu from 'svelte-material-icons/Menu.svelte';
	import type { DrawerSettings } from '@skeletonlabs/skeleton';
	import Linkedin from 'svelte-material-icons/Linkedin.svelte';
	import Instagram from 'svelte-material-icons/Instagram.svelte';
	import Post from 'svelte-material-icons/Post.svelte';
	import hljs from 'highlight.js';
	import 'highlight.js/styles/github-dark.css';
	import { storeHighlightJs } from '@skeletonlabs/skeleton';
	import { fade } from 'svelte/transition'

	export let data

	storeHighlightJs.set(hljs);
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
		<button class="btn variant-filled mx-4 my-2" data-sveltekit-preload-data="hover" on:click={() => window.open('/', '_self')}>
			<span><Home {size} {viewBox} /></span>
		</button>
		<br>
		<button class="btn variant-filled mx-4 my-2" data-sveltekit-preload-data="hover" on:click={() => window.open('/blog', '_self')}>
			<span><Post {size} {viewBox} /></span>
		</button>
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

<AppShell>
	<svelte:fragment slot="header">
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
			<svelte:fragment slot="trail">
				<LightSwitch />
			</svelte:fragment>
		</AppBar>
		{/if}
	</svelte:fragment>
	<svelte:fragment slot="sidebarLeft">
		{#if innerWidth > 640}
		<AppRail class="fixed z-10">
			<AppRailAnchor href="/" target="_self" title="Home">
				<svelte:fragment slot="lead">
					<span><Home {size} {viewBox} /></span>
				</svelte:fragment>
				<span>Home</span>
			</AppRailAnchor>
			<AppRailAnchor href="/blog" target="_self" title="Instagram">
				<svelte:fragment slot="lead">
					<span><Post {size} {viewBox} /></span>
				</svelte:fragment>
				<span>Blog</span>
			</AppRailAnchor>
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
				<AppRailAnchor>
					<svelte:fragment slot="lead"><LightSwitch /></svelte:fragment>
				</AppRailAnchor>
			</svelte:fragment>
		</AppRail>
		{/if}
	</svelte:fragment>
	{#key data.currentRoute}
	<main in:fade={{ duration: 150, delay: 150 }} out:fade={{ duration: 150 }}>
		<div class="container" style={`${innerWidth > 640 ? "padding-left: 88px;" : ""}`}>
			<slot />
		</div>
	</main>
	{/key}
	<svelte:fragment slot="pageFooter"></svelte:fragment>
</AppShell>
