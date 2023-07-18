<script lang="ts">
	import { marked } from 'marked';

	marked.use({mangle: false, headerIds: false});
	let overviewDarkMode = '![](https://raw.githubusercontent.com/mirhasalh/github-stats/master/generated/overview.svg#gh-dark-mode-only)';
	let overviewLightMode = '![](https://raw.githubusercontent.com/mirhasalh/github-stats/master/generated/overview.svg#gh-light-mode-only)';
	let languagesDarkMode = '![](https://raw.githubusercontent.com/mirhasalh/github-stats/master/generated/languages.svg#gh-dark-mode-only)';
	let languagesLightMode = '![](https://raw.githubusercontent.com/mirhasalh/github-stats/master/generated/languages.svg#gh-light-mode-only)';
	export let data;
</script>

<div class="p-8 space-y-5">
	<h1 class="h1">Blog posts</h1>
	<ul class="list">
		{#each data.posts as post}
			<li>
				<span><a class="anchor h3" href={post.path}>{post.meta.title}</a><br><p>Published {post.meta.date}</p></span>
			</li>
		{/each}
	</ul>
	<h1 class="h1">GitHub stats visualization</h1>
	<p>Here's my GitHub stats generated from my public repositories:</p>
	<table>
		<tbody>
		  <tr class="collapse dark:visible">
			<td>{@html marked(overviewDarkMode)}</td>
		  </tr>
		  <tr class="visible dark:collapse">
			<td>{@html marked(overviewLightMode)}</td>
		  </tr>
		  <tr class="collapse dark:visible">
			<td>{@html marked(languagesDarkMode)}</td>
		  </tr>
		  <tr class="visible dark:collapse">
			<td>{@html marked(languagesLightMode)}</td>
		  </tr>
		</tbody>
	  </table>
</div>
