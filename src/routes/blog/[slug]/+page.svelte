<script>
	export let data;
</script>

<article class="p-8 space-y-5">
	<h1 class="h1">{data.title}</h1>
	<span class="text-sm opacity-50">Published: {data.date}</span>
	<svelte:component this={data.content} />
</article>
