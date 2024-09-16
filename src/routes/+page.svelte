<script lang="ts">
	import Icon from '@iconify/svelte';
	import type { Project } from '$lib/types';
	// import Impressum from '$lib/impressum.svelte';
	// import Privacy from '$lib/privacy.svelte';
	// import projectModal from '$lib/projectModal.svelte';

	function openProjectModal(project: Project) {}

	const icons = [
		{
			name: 'Email',
			label: 'info@foramitti.org',
			href: 'mailto:info@foramitti.org',
			icon: 'bi:envelope-at-fill'
		},
		{
			name: 'GitHub',
			label: 'github.com/jofmi',
			href: 'https://github.com/jofmi',
			icon: 'bi:github'
		},
		{
			name: 'LinkedIn',
			label: 'linkedin.com/in/joelforamitti/',
			href: 'https://www.linkedin.com/in/joelforamitti/',
			icon: 'bi:linkedin'
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
			name: 'raumcoop',
			logo: 'images/logos/raumcoop.png',
			href: 'https://raumcoop.at/'
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
		},
		{
			name: 'stape',
			logo: 'images/logos/stape.png',
			href: 'https://www.stape.eu/'
		}
	];

	const projects: Project[] = [
		{
			date: '2022-2024',
			title: 'Mein MILA',
			tags: ['Open-Source'],
			summary: 'Mitgliederplattform und Datenbanksystem für den MILA Mitmach-Supermarkt',
			description: `Die MILA Mitgliederplattform "Mein MILA" ist ein partizipatives Tool für den [MILA-Mitmach-Supermarkt e. G.](https://mila.wien). Über die Plattform können Nutzer\*innen einen Beitrittsantrag stellen, sich für Arbeitsschichten und Urlaube eintragen sowie ihre persönlichen Daten aktualisieren.

Das Backend der Plattform ist ein umfassendes Datenbanksystem, das zur Verwaltung von Mitgliederdaten, Rechnungen, Arbeitsschichten und automatischem E-Mail-Versand dient.

Die Mitgliederplattform ist seit 2022 aktiv für die über 700 Mitglieder der Genossenschaft im Einsatz und wird laufend erweitert. 

Dieses Projekt wurde vom [AK Digifond](https://wien.arbeiterkammer.at/digifonds) gefördert und in Zusammenarbeit mit [convive*](https://www.convive.io/) realisiert.

**Open-Source Technologien**: Nuxt, Keycloak, Directus, PostgreSQL, Docker`,
			repositoryUrl: 'https://github.com/MILA-Wien/mila-server',
			images: [
				'images/projects/meinmila_1.png',
				'images/projects/meinmila_2.png',
				'images/projects/meinmila_3.png'
			]
		},
		{
			date: '2023',
			title: 'Augustina',
			summary: 'Bargeldloses Bezahlsystem und Verwaltungsoberfläche für Straßenzeitungen',
			tags: ['Open-Source'],
			description: `Das Bezahlsystem Augustina wurde 2023 für die Straßenzeitung Augustin entwickelt und ist seitdem aktiv im Einsatz. Es ermöglicht bargeldlose Zahlungen auf der Straße und dient gleichzeitig als Online-Shop und Verwaltungssystem.

Dieses Projekt wurde vom [AK Digifond](https://wien.arbeiterkammer.at/digifonds) gefördert und in Zusammenarbeit mit [convive*](https://www.convive.io/) realisiert.

**Augustin Blog:** [Mit Bargeld oder Karte?](https://augustin.or.at/mit-bargeld-oder-karte/)

**Open-Source Technologien**: Vue, Go, PostgreSQL, Docker`,
			repositoryUrl: 'https://github.com/augustin-wien/augustina-backend'
		},
		{
			repositoryUrl: 'https://github.com/jofmi/agentpy',
			title: 'AgentPy',
			date: '2021',
			summary: 'Wissenschaftliches Software-Paket für agenten-basierte Simulationsmodelle',
			description: `AgentPy ist ein Open-Source-Paket für die Entwicklung und Analyse agenten-basierter Modelle in Python. Das Framework integriert die Aufgaben der Modellgestaltung, interaktiver Simulationen, numerischer Experimente und Datenanalyse in einer einzigen Entwicklungs-Umgebung. Das Paket ist für interaktives Programmieren mit IPython und Jupyter optimiert.

Dokumentation: [agentpy.readthedocs.io](https://agentpy.readthedocs.io)			`,
			tags: ['Open-Source', 'Python']
		}
	];
</script>

<div class="mx-auto flex h-full items-center justify-center">
	<div class="lg:mt-35 w-full max-w-5xl space-y-10 p-10 sm:space-y-20 md:p-24">
		<div id="pf-title" class="flex flex-row items-center justify-between gap-5 md:gap-10">
			<div class="w-2/3">
				<h1 class="h1 mb-2">Joël Foramitti</h1>
				<p class="mb-4 text-xl italic md:text-2xl">Ökologischer Ökonom & Software Entwickler</p>
				<div class="justify-left flex flex-wrap space-x-4 text-3xl">
					{#each icons as { name, icon, href }}
						<a {href} target="_blank"><Icon {icon} class="duration-100 hover:scale-[1.04]" /></a>
					{/each}
				</div>
			</div>
			<div class="drop-shadow-md">
				<img src="images/joel.jpg" alt="Joël Foramitti" class="w-40 overflow-hidden rounded-full" />
			</div>
		</div>

		<div id="pf-intro" class="space-y-4">
			<p class="text-lg">
				Hallo! Ich forsche zu alternativen Wirtschaftsformen und unterstütze Organisationen bei der
				Entwicklung von digitalen Lösungen für Partizipationsprozesse und Selbstorganisation. Mein
				Schwerpunkt liegt dabei auf Projekten für <a
					href="https://se-conference.uni-graz.at/de/politik/oesterreich/#c541464"
					target="_blank"
					class="font-bold italic"
					>gemeinschaftliches, ökologisches und bedürfnis-orientiertes Wirtschaften</a
				>.
			</p>
		</div>

		<!-- Offers block -->
		<div id="pf-services" class="space-y-6">
			<h2 class="h2">Angebote</h2>

			<div class="grid grid-cols-1 gap-5 sm:grid-cols-2">
				<div class="pf-box w-full space-y-2 px-6 py-5">
					<h3 class="h3">Software-Entwicklung</h3>
					<p class="text-md">
						Ich biete maßgeschneiderte Lösungen für Datenbanken, Apps und digitale Plattformen mit
						einem Fokus auf Open-Source Technologien.
					</p>
					<p class="text-md">
						Dabei begleite ich den gesamten Entwicklungs-Prozess von der gemeinsamen Konzeption bis
						zur Umsetzung und langfristigen Wartung.
					</p>
				</div>

				<div class="pf-box w-full space-y-2 px-6 py-5">
					<h3 class="h3">Forschung & Beratung</h3>
					<p>
						Ich biete Unterstützung bei der Entwicklung von Strukturen und Prozessen und für
						Partizipation und Selbstorganisation.
					</p>
					<p>
						Darüber hinaus biete ich Forschungsleistungen wie Workshops, Umfragen, Datenerhebungen,
						Analysen und Simulationen an.
					</p>
				</div>
			</div>
		</div>

		<!-- References block -->
		<div id="projects" class="space-y-6">
			<h2 class="h2">Projekte</h2>

			<div id="projects" class="grid grid-cols-1 gap-5 sm:grid-cols-2 lg:grid-cols-3">
				{#each projects as project}
					<button on:click={() => openProjectModal(project)}>
						<div class="pf-box h-full space-y-2 px-6 py-5">
							<div class="m-1 flex flex-col space-y-2">
								<h3 class="h3">{project.title}</h3>
								<p class="text-sm italic">{project.date}</p>
								<p>{project.summary}</p>
							</div>
						</div>
					</button>
				{/each}
			</div>
		</div>

		<!-- Partners block -->
		<div id="partners" class="space-y-6">
			<h2 class="h2">Partner*innen</h2>
			<div class="grid grid-cols-1 gap-5 sm:grid-cols-2 lg:grid-cols-3">
				{#each partners as { name, href, logo }}
					<a {href} target="_blank">
						<div class="pf-box flex h-36 items-center">
							<img src={logo} alt={name} class="m-auto max-h-[7rem] max-w-[10rem]" />
						</div>
					</a>
				{/each}
			</div>
		</div>

		<!-- Background block -->
		<div id="pf-cv" class="space-y-6">
			<h2 class="h2">Hintergrund</h2>
			<ul class="text-md pf-box list-inside list-disc p-5">
				<li>
					<span class="font-bold">02.2024 - heute</span>: Selbstständig als Software-Entwickler &
					Ökologischer Ökonom
				</li>
				<li>
					<span class="font-bold">09.2022 - heute</span>: Operatives Team, MILA Mitmach-Supermarkt
					e. G.
				</li>
				<li>
					<span class="font-bold">09.2018 - 09.2022</span>: Ph.D. Ökologische Ökonomik, Vrije
					Universiteit Amsterdam
				</li>
				<li>
					<span class="font-bold">09.2017 - 05.2018</span>: M.Sc. Umweltwissenschaften, Universitat
					Autònoma de Barcelona
				</li>
				<li>
					<span class="font-bold">10.2013 - 01.2017</span>: B.Sc. Technische Physik, Technische
					Universität Wien
				</li>
			</ul>
		</div>

		<div>
			<a href="mailto:info@foramitti.org">
				<div
					class="btn center flex w-full items-center justify-center gap-2 rounded-md bg-primary px-6 py-5 text-lg font-bold text-white drop-shadow-md transition hover:scale-[1.02] md:text-2xl"
				>
					<Icon icon="bi:envelope-at-fill" class="mr-2" /> Jetzt Kontakt aufnehmen
				</div>
			</a>
		</div>

		<div class="pf-box flex flex-wrap items-end px-6 py-5 text-lg">
			<div class="w-full sm:w-1/2">
				<span class="font-semibold">Joël Foramitti, Ph.D.</span>
				{#each icons as { label, icon, href }}
					<a {href} target="_blank" class="flex flex-row items-center gap-2">
						<Icon {icon} class="" />
						{label}
					</a>
				{/each}
			</div>
			<div class="grow"></div>
			<div class="flex flex-col items-start sm:items-end">
				<!-- on:click={} -->
				<button class="link-on-white"> Impressum </button>
				<button class="link-on-white"> Datenschutz </button>
			</div>
		</div>
	</div>
</div>

<style>
	.pf-box {
		@apply rounded-md bg-white/60 text-left text-black drop-shadow-sm duration-150 hover:bg-white;
	}

	.link-on-white {
		@apply font-semibold no-underline;
	}
</style>
