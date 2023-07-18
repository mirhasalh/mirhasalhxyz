<script>
	export let data;
</script>

<div class="p-8 space-y-5">
	<h1 class="h1">Blog</h1>
	<ul class="list">
		{#each data.posts as post}
			<li>
				<span><a class="anchor h3" href={post.path}>{post.meta.title}</a><br><p>Published {post.meta.date}</p></span>
			</li>
		{/each}
	</ul>
</div>

