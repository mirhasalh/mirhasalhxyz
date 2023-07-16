<script>
	export let data;
</script>

<article class="p-8 space-y-5">
	<h1 class="h1">{data.title}</h1>
	<span class="badge variant-filled-primary">Published: {data.date}</span>
	<svelte:component this={data.content} />
</article>
