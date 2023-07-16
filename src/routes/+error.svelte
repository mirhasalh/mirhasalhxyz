<script>
	import { page } from '$app/stores';
</script>

<div class="fixed top-1/2 left-1/2 -translate-y-1/2 -translate-x-1/2 text-center">
	<h1 class="h1">{$page.status}</h1>
	<p>{$page.error.message}</p>
</div>
