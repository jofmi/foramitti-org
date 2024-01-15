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

	const projects = [
		{
			logo: 'images/logos/collectivo.png',
			href: 'https://collectivo.io',
			date: '2022 - heute',
			title: 'Collectivo',
			subtitle:
				'Open-Source Plattform für Zusammenarbeit, Partizipation und Datenverwaltung'
		},
		{
			href: 'https://augustin.or.at/mit-bargeld-oder-karte/',
			title: 'Augustina',
			date: '2023',
			subtitle: 'Bargeldloses Bezahlsystem für den Augustin'
		},
		{
			href: 'https://agentpy.readthedocs.io/en/latest/',
			title: 'AgentPy',
			date: '2021',
			subtitle:
				'Open-Source Paket für die Simulation von Agenten-basierten Modellen'
		}
	];
</script>

<div class="h-full mx-auto flex justify-center items-center">
	<div class="space-y-5 max-w-3xl w-full m-10 md:m-24 lg:mt-48">
		<div>
			<h1 class="h1 mb-2">Joël Foramitti</h1>
			<p class="text-xl">Wissen und Werkzeuge für kooperatives Wirtschaften</p>
		</div>
		<div class="flex flex-wrap justify-left text-3xl space-x-4">
			{#each icons as { name, icon, href }}
				<a {href} target="_blank"
					><Icon {icon} class="hover:scale-[1.04] duration-100" /></a
				>
			{/each}
		</div>

		<div class="h-5"></div>

		<p>
			Hallo! Ich bin promovierter Wirtschaftsforscher, Software-Entwickler, und
			Berater. Ich unterstütze Organisationen bei der Entwicklung von Prozessen
			und Strukturen sowie bei der Umsetzung von maßgeschneiderten
			Software-Lösungen. Mein Schwerpunkt und meine Leidenschaft liegen dabei
			auf Projekten für <a
				href="https://se-conference.uni-graz.at/de/politik/oesterreich/#c541464"
				target="_blank"
				class="font-bold"
				>gemeinschaftliches, nachhaltiges und bedürfnis-orientiertes
				Wirtschaften</a
			>.
		</p>

		<div>
			<a href="mailto:joel@foramitti.org">
				<button
					type="button"
					class="btn variant-filled rounded-md hover:scale-[1.04] duration-100 font-bold pf-shadow"
				>
					<Icon icon="bi:envelope-at-fill" class="mr-2" /> Kontakt aufnehmen
				</button>
			</a>
		</div>

		<div class="pf-divider"></div>

		<h2 class="h2">Partner*innen</h2>
		<div
			id="pf-partners"
			class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5"
		>
			{#each partners as { name, href, logo }}
				<a {href} target="_blank">
					<div class="pf-card pf-shadow h-36 flex items-center">
						<img src={logo} alt={name} class="m-auto max-h-[7rem] max-w-48" />
					</div>
				</a>
			{/each}
		</div>

		<div class="pf-divider"></div>

		<h2 class="h2">Projekte</h2>

		<div
			id="pf-projects"
			class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5"
		>
			{#each projects as { title, subtitle, date, href }}
				<a {href} target="_blank">
					<div class="pf-card pf-shadow h-full">
						<div class="flex flex-col space-y-2 m-1">
							<h3 class="h3">{title}</h3>
							<p class="text-sm italic">{date}</p>
							<p>{subtitle}</p>
						</div>
					</div>
				</a>
			{/each}
		</div>

		<div class="pf-divider"></div>

		<h2 class="h2">Impressum</h2>
		<p>
			<span class="">Dr. Joël Foramitti</span> <br />

			<a href="mailto:joel@foramitti.org" class="font-bold"
				>joel@foramitti.org</a
			>
		</p>
		<p>
			<span class="">smart@work GmbH</span>
			<br />Gumpendorferstraße 63b
			<br />1060 Wien
		</p>
		<p>
			UID Nr.: ATU75116919
			<br />FN 525600 t
		</p>
	</div>
</div>

<style lang="postcss">
	.pf-divider {
		@apply h-5;
	}

	.pf-shadow {
		@apply shadow-[1px_1px_15px_3px] shadow-white/20;
	}

	.pf-card {
		@apply bg-white text-black rounded-md duration-300 transition-all px-4 py-3 hover:scale-[1.03];
	}
</style>
