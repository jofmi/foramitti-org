<script lang="ts">
	import Icon from '@iconify/svelte';
	import { initializeStores } from '@skeletonlabs/skeleton';
	import { Modal, getModalStore } from '@skeletonlabs/skeleton';
	import type { Project } from '$lib/types';
	import Impressum from '$lib/impressum.svelte';
	import Privacy from '$lib/privacy.svelte';
	import projectModal from '$lib/projectModal.svelte';

	initializeStores();
	const modalStore = getModalStore();

	function openProjectModal(project: Project) {
		modalStore.trigger({
			type: 'component',
			component: {
				ref: projectModal,
				props: { project: project }
			}
		});
	}

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
			summary:
				'Mitgliederplattform und Datenbanksystem für den MILA Mitmach-Supermarkt',
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
			summary:
				'Bargeldloses Bezahlsystem und Verwaltungsoberfläche für Straßenzeitungen',
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
			summary:
				'Wissenschaftliches Software-Paket für agenten-basierte Simulationsmodelle',
			description: `AgentPy ist ein Open-Source-Paket für die Entwicklung und Analyse agenten-basierter Modelle in Python. Das Framework integriert die Aufgaben der Modellgestaltung, interaktiver Simulationen, numerischer Experimente und Datenanalyse in einer einzigen Entwicklungs-Umgebung. Das Paket ist für interaktives Programmieren mit IPython und Jupyter optimiert.

Dokumentation: [agentpy.readthedocs.io](https://agentpy.readthedocs.io)			`,
			tags: ['Open-Source', 'Python']
		}
	];
</script>

<Modal />
<!-- <Modal components={modalRegistry} /> -->

<div class="h-full mx-auto flex justify-center items-center">
	<div class="space-y-10 sm:space-y-20 max-w-5xl w-full p-10 md:p-24 lg:mt-35">
		<div
			id="pf-title"
			class="flex flex-row gap-5 md:gap-10 items-center justify-between"
		>
			<div class="w-2/3">
				<h1 class="h1 mb-2">Joël Foramitti</h1>
				<p class="text-xl md:text-2xl italic mb-4">
					Ökologischer Ökonom & Software Entwickler
				</p>
				<div class="flex flex-wrap justify-left text-3xl space-x-4">
					{#each icons as { name, icon, href }}
						<a {href} target="_blank"
							><Icon {icon} class="hover:scale-[1.04] duration-100" /></a
						>
					{/each}
				</div>
			</div>
			<div class="drop-shadow-md">
				<img
					src="images/joel.jpg"
					alt="Joël Foramitti"
					class="rounded-full w-40 overflow-hidden"
				/>
			</div>
		</div>

		<div id="pf-intro" class="space-y-4">
			<p class="text-lg">
				Hallo! Ich forsche zu alternativen Wirtschaftsformen und unterstütze
				Organisationen bei der Entwicklung von digitalen Lösungen für
				Partizipationsprozesse und Selbstorganisation. Mein Schwerpunkt liegt
				dabei auf Projekten für <a
					href="https://se-conference.uni-graz.at/de/politik/oesterreich/#c541464"
					target="_blank"
					class="font-bold italic"
					>gemeinschaftliches, ökologisches und bedürfnis-orientiertes
					Wirtschaften</a
				>.
			</p>
		</div>

		<!-- Offers block -->
		<div id="pf-services" class="space-y-6">
			<h2 class="h2">Angebote</h2>

			<div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
				<div class="pf-box w-full px-6 py-5 space-y-2">
					<h3 class="h3">Software-Entwicklung</h3>
					<p class="text-md">
						Ich biete maßgeschneiderte Lösungen für Datenbanken, Apps und
						digitale Plattformen mit einem Fokus auf Open-Source Technologien.
					</p>
					<p class="text-md">
						Dabei begleite ich den gesamten Entwicklungs-Prozess von der
						gemeinsamen Konzeption bis zur Umsetzung und langfristigen Wartung.
					</p>
				</div>

				<div class="pf-box w-full px-6 py-5 space-y-2">
					<h3 class="h3">Forschung & Beratung</h3>
					<p>
						Ich biete Unterstützung bei der Entwicklung von Strukturen und
						Prozessen und für Partizipation und Selbstorganisation.
					</p>
					<p>
						Darüber hinaus biete ich Forschungsleistungen wie Workshops,
						Umfragen, Datenerhebungen, Analysen und Simulationen an.
					</p>
				</div>
			</div>
		</div>

		<!-- References block -->
		<div id="projects" class="space-y-6">
			<h2 class="h2">Projekte</h2>

			<div
				id="projects"
				class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5"
			>
				{#each projects as project}
					<button on:click={() => openProjectModal(project)}>
						<div class="pf-box h-full px-6 py-5 space-y-2">
							<div class="flex flex-col space-y-2 m-1">
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
			<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5">
				{#each partners as { name, href, logo }}
					<a {href} target="_blank">
						<div class="pf-box h-36 flex items-center">
							<img
								src={logo}
								alt={name}
								class="m-auto max-h-[7rem] max-w-[10rem]"
							/>
						</div>
					</a>
				{/each}
			</div>
		</div>

		<!-- Background block -->
		<div id="pf-cv" class="space-y-6">
			<h2 class="h2">Hintergrund</h2>
			<ul class="list-inside list-disc text-md pf-box p-5">
				<li>
					<span class="font-bold">02.2024 - heute</span>: Selbstständig als
					Software-Entwickler & Ökologischer Ökonom
				</li>
				<li>
					<span class="font-bold">09.2022 - heute</span>: Operatives Team, MILA
					Mitmach-Supermarkt e. G.
				</li>
				<li>
					<span class="font-bold">09.2018 - 09.2022</span>: Ph.D. Ökologische
					Ökonomik, Vrije Universiteit Amsterdam
				</li>
				<li>
					<span class="font-bold">09.2017 - 05.2018</span>: M.Sc.
					Umweltwissenschaften, Universitat Autònoma de Barcelona
				</li>
				<li>
					<span class="font-bold">10.2013 - 01.2017</span>: B.Sc. Technische
					Physik, Technische Universität Wien
				</li>
			</ul>
		</div>

		<div>
			<a href="mailto:info@foramitti.org">
				<button
					type="button"
					class="btn font-bold text-lg md:text-2xl rounded-md bg-primary-900 drop-shadow-md w-full px-6 py-5 text-white center"
				>
					<Icon icon="bi:envelope-at-fill" class="mr-2" /> Jetzt Kontakt aufnehmen
				</button>
			</a>
		</div>

		<div class="pf-box px-6 py-5 text-lg flex flex-wrap items-end">
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
				<button
					class="link-on-white"
					on:click={() =>
						modalStore.trigger({
							type: 'component',
							component: { ref: Impressum }
						})}
				>
					Impressum
				</button>
				<button
					class="link-on-white"
					on:click={() =>
						modalStore.trigger({
							type: 'component',
							component: { ref: Privacy }
						})}
				>
					Datenschutz
				</button>
			</div>
		</div>
	</div>
</div>

<style lang="postcss">
	.pf-box {
		@apply bg-white/60 hover:bg-white duration-150 drop-shadow-sm rounded-md text-black text-left;
	}

	.link-on-white {
		@apply no-underline font-semibold text-primary-900;
		color: --theme-font-color-base;
	}
</style>
