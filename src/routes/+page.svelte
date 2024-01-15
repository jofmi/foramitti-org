<script lang="ts">
	import Icon from '@iconify/svelte';
	const icons = [
		{
			name: 'GitHub',
			href: 'https://github.com/jofmi',
			icon: 'bi:github'
		},
		{
			name: 'LinkedIn',
			href: 'https://www.linkedin.com/in/joelforamitti/',
			icon: 'bi:linkedin'
		},
		{
			name: 'Email',
			href: 'mailto:joel@foramitti.org',
			icon: 'bi:envelope-at-fill'
		}
	];

	const partners = [
		{
			name: 'mila',
			logo: 'images/logos/mila.png',
			href: 'https://mila.wien'
		},
		{
			name: 'radius',
			logo: 'images/logos/radius.png',
			href: 'https://radius.co.at'
		},
		{
			name: 'convive',
			logo: 'images/logos/convive.svg',
			href: 'https://convive.io'
		},
		{
			name: 'smart',
			logo: 'images/logos/smart.svg',
			href: 'https://smartat.coop'
		}
	];
</script>

<div class="h-full mx-auto flex justify-center items-center">
	<div class="space-y-5 max-w-3xl w-full m-10 md:m-24 lg:mt-48">
		<h1 class="h1">Joël Foramitti</h1>
		<p class="text-xl">Wissen und Werkzeuge für kooperatives Wirtschaften</p>

		<div class="flex flex-wrap justify-left text-3xl space-x-4">
			{#each icons as { name, icon, href }}
				<a {href} target="_blank"
					><Icon {icon} class="hover:scale-[1.04] duration-100" /></a
				>
			{/each}
		</div>

		<div class="h-5"></div>

		<p>
			Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
			eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
			voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
			clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
			amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
			nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed
			diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum.
			Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor
			sit amet.
		</p>

		<div class="h-5"></div>

		<h2 class="h2">Partner*innen</h2>
		<div
			id="partners"
			class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5"
		>
			{#each partners as { name, href, logo }}
				<a {href} target="_blank">
					<div class="pf-card flex items-center">
						<img src={logo} alt={name} class="m-auto max-h-[7rem] max-w-48" />
					</div>
				</a>
			{/each}
		</div>
	</div>
</div>

<style lang="postcss">
	.pf-card {
		@apply bg-white rounded-md h-36 duration-300 transition-all px-4 py-3 hover:scale-[1.03] shadow-[1px_1px_15px_3px] shadow-white/20;
	}

	.pf-shadow {
		@apply shadow-[1px_1px_15px_3px] shadow-white/20 hover:shadow-white/35 hover:shadow-[1px_1px_15px_5px];
	}
</style>
