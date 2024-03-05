<script>
	import { dev } from "$app/environment"

	const title = "Makers Forge"
	const description = "Helping makers grow 🌱"
	const url = dev ? "http://localhost:5173" : "https://makersforge.io"
</script>

<svelte:head>
	<title>{title}</title>

	<meta name="description" content={description} />

	<meta property="og:type" content="article" />
	<meta property="og:url" content={`${url}/blog`} />
	<meta property="og:title" content={title} />
	<meta property="og:description" content={description} />
	<meta property="og:site_name" content={title} />
	<meta property="og:image" content="/makers_forge_logo.png" />

	<!--	TODO: Replace these with Makers Forge twitter handle-->
	<!--	<meta name="twitter:site" content="@McBride1105" />-->
	<!--	<meta name="twitter:creator" content="@McBride1105" />-->
	<meta name="twitter:title" content={title} />
	<meta name="twitter:description" content={description} />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:image:src" content="/makers_forge_logo.png" />
	<meta name="twitter:widgets:new-embed-design" content="on" />

	<meta name="theme-color" content="#ffffff" media="(prefers-color-scheme: light)" />
	<meta name="theme-color" content="#000000" media="(prefers-color-scheme: dark)" />
</svelte:head>

<div class="container h-full mx-auto drape">
	<div class="my-5">
		<h1 class="h1">Makers Forge</h1>
	</div>
</div>
