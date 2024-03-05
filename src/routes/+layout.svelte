<script>
	import "../app.pcss"

	// Highlight JS
	import hljs from "highlight.js/lib/core"
	import "highlight.js/styles/github-dark.css"
	import { storeHighlightJs } from "@skeletonlabs/skeleton"
	import xml from "highlight.js/lib/languages/xml" // for HTML
	import css from "highlight.js/lib/languages/css"
	import javascript from "highlight.js/lib/languages/javascript"
	import typescript from "highlight.js/lib/languages/typescript"
	import { AppShell, AppBar } from "@skeletonlabs/skeleton"
	import { afterNavigate } from "$app/navigation"
	import { GithubSolid, MailBoxSolid } from "flowbite-svelte-icons"

	afterNavigate((params) => {
		const isNewPage = params.from?.url.pathname !== params.to?.url.pathname
		const elemPage = document.querySelector("#page")
		if (isNewPage && elemPage !== null) {
			elemPage.scrollTop = 0
		}
	})

	hljs.registerLanguage("xml", xml) // for HTML
	hljs.registerLanguage("css", css)
	hljs.registerLanguage("javascript", javascript)
	hljs.registerLanguage("typescript", typescript)
	storeHighlightJs.set(hljs)

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from "@floating-ui/dom"
	import { storePopup } from "@skeletonlabs/skeleton"
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow })
</script>

<AppShell class="max-w-[100vw] min-h-[100vh]">
	<svelte:fragment slot="header">
		<AppBar>
			<svelte:fragment slot="lead">
				<div class="row space-x-2">
					<img class="w-6" src="/makers_forge_logo.png" alt="makers forge logo" />
					<div>Makers Forge</div>
				</div>
			</svelte:fragment>

			<svelte:fragment slot="trail">
				<a
					href="https://github.com/JimmyMcBride/makers-forge"
					class="badge-icon variant-filled"
					target="_blank"
				>
					<GithubSolid />
				</a>
				<a href="mailto:hello@makersforge.io" class="badge-icon variant-filled">
					<MailBoxSolid />
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<slot />
	<svelte:fragment slot="pageFooter">
		<div class="m-4 row justify-center">
			<p>&copy; 2024 Makers Forge. All rights reserved.</p>
		</div>
	</svelte:fragment>
</AppShell>
