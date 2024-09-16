<script lang="ts">
	import Icon from '@iconify/svelte';
	import type { Project } from '$lib/types';
	import * as Dialog from '$lib/components/ui/dialog';
	import { marked } from 'marked';

	const renderer: any = {
		link(href: any) {
			const link = marked.Renderer.prototype.link.call(this, href);
			return link.replace('<a', "<a target='_blank' class='marked-link'");
		}
	};

	let imageModalOpen = false;
	function setOpen() {
		imageModalOpen = !imageModalOpen;
	}
	let imageModalSrc = '';

	marked.use({ renderer });

	const impressum = `# Impressum
Informationspflicht laut §5 E-Commerce Gesetz, §14 Unternehmensgesetzbuch,
§63 Gewerbeordnung und Offenlegungspflicht laut §25 Mediengesetz.

Joël Foramitti  
Tivoligasse 38/1/7  
1120 Wien  
Österreich

Unternehmensgegenstand: IT Dienstleistungen  
UID-Nummer: ATU80431267  
E-Mail: info@foramitti.org`;

	const privacy = `# Datenschutzerklärung

## Datenschutz

Der Schutz Ihrer persönlichen Daten ist uns wichtig. Wir verarbeiten Ihre
Daten auf Grundlage der geltenden gesetzlichen Bestimmungen (EU
Datenschutz-Grundverordnung DSGVO, TKG 2003). In diesen
Datenschutzinformationen informieren wir Sie über die wichtigsten Aspekte
der Datenverarbeitung im Rahmen unserer Website.

Die Nutzung unserer Webseite ist in der Regel ohne die Angabe
personenbezogener Daten möglich. Sollten Sie, z.B. zum Zwecke der
Kontaktaufnahme persönliche Daten eingeben, geben wir die notwendigen
Informationen an Firmen weiter, die in unserem Auftrag Daten verarbeiten
(z.B. unser Email und Cloud Anbieter). Wir beauftragen ausschließlich
Firmen, die sich der EU Datenschutz-Grundverordnung unterwerfen.

## Server Protokolle

Der Server, von dem diese Webseite bereitgestellt wird, speichert
Informationen die von Ihrem Browser automatisch an uns übermittelt werden,
in sogenannten Log-Files. Diese Daten dienen der technischen Überwachung
des Webservers. Sie beinhalten folgende Informationen: Browsertyp und
Browserversion, Verwendetes Betriebssystem, Referrer URL (also die Seite,
von der Sie zu uns gekommen sind), Die IP Adresse des zugreifenden
Computers, Uhrzeit der Anfrage

## Verschlüsselte Übertragung

Diese Webseite nutzt aus Gründen der Sicherheit und des Datenschutzes eine
SSL Verschlüsselung, die verhindert, dass Dritte die von Ihnen
eingegebenen Daten auf dem Übertragungsweg abfangen und lesen können. Sie
erkennen die aktive Verschlüsselung an dem grünen Vorhängeschloss oder
ähnlichen Symbolen in der Adresszeile Ihres Browsers.

## Ihre Rechte

Ihnen stehen grundsätzlich die Rechte auf Auskunft, Berichtigung,
Löschung, Einschränkung, Datenübertragbarkeit, Widerruf und Widerspruch
zu. Wenn Sie glauben, dass die Verarbeitung Ihrer Daten gegen das
Datenschutzrecht verstößt oder Ihre datenschutzrechtlichen Ansprüche sonst
in einer Weise verletzt worden sind, können Sie sich bei der
Aufsichtsbehörde beschweren. In Österreich ist dies die
Datenschutzbehörde.
`;

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

<Dialog.Root open={imageModalOpen} onOpenChange={setOpen}>
	<Dialog.ContentWide>
		<img src={imageModalSrc} alt="Project" class=" rounded-md object-contain" />
	</Dialog.ContentWide>
</Dialog.Root>

<div class="mx-auto flex h-full items-center justify-center">
	<div class="lg:mt-35 w-full max-w-5xl space-y-10 p-10 sm:space-y-20 md:p-24">
		<div id="pf-title" class="flex flex-row items-center justify-between gap-5 md:gap-10">
			<div class="w-2/3">
				<h1 class="h1 mb-2">Joël Foramitti</h1>
				<p class="mb-4 text-xl italic md:text-2xl">Ökologischer Ökonom & Software Entwickler</p>
				<div class="justify-left flex flex-wrap space-x-4 text-3xl">
					{#each icons as { name, icon, href }}
						<a {href} target="_blank"><Icon {icon} class="" /></a>
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
					<Dialog.Root>
						<Dialog.Trigger>
							<div class="pf-box h-full space-y-2 px-6 py-5">
								<div class="m-1 flex flex-col space-y-2">
									<h3 class="h3">{project.title}</h3>
									<p class="text-sm italic">{project.date}</p>
									<p>{project.summary}</p>
								</div>
							</div>
						</Dialog.Trigger>
						<Dialog.Content>
							<div class="flex flex-row justify-between">
								<h2 class="h2">{project.title}</h2>
								<a href={project.repositoryUrl} target="_blank">
									<Icon icon="bi:github" class="text-4xl duration-100 " />
								</a>
							</div>
							<div class="flex flex-wrap gap-2 pb-4" id="modal-tags">
								<span class="rounded bg-slate-200 px-2 py-1">{project.date}</span>
								{#each project.tags || [] as tag}
									<span class="rounded bg-slate-200 px-2 py-1">{tag}</span>
								{/each}
							</div>

							{@html marked(project.description)}

							{#if project.images && project.images.length > 0}
								<div class="flex flex-wrap gap-4 pt-6">
									{#each project.images as image}
										<button
											on:click={() => {
												imageModalSrc = image;
												imageModalOpen = true;
											}}
											><img
												src={image}
												alt={project.title}
												class=" h-56 rounded-md object-contain"
											/></button
										>
									{/each}
								</div>
							{/if}
						</Dialog.Content>
					</Dialog.Root>
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
					class="btn center flex w-full items-center justify-center gap-2 rounded-md bg-primary px-6 py-5 text-lg font-bold text-white drop-shadow-md transition hover:bg-primary/90 md:text-2xl"
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
				<Dialog.Root>
					<Dialog.Trigger><div class="link-on-white">Impressum</div></Dialog.Trigger>
					<Dialog.Content>
						{@html marked(impressum)}
					</Dialog.Content>
				</Dialog.Root>
				<Dialog.Root>
					<Dialog.Trigger><div class="link-on-white">Datenschutz</div></Dialog.Trigger>
					<Dialog.Content>
						{@html marked(privacy)}
					</Dialog.Content>
				</Dialog.Root>
			</div>
		</div>
	</div>
</div>

<style>
	.pf-box {
		@apply rounded-md bg-white/60 text-left text-black drop-shadow-md duration-150 hover:bg-white/80;
	}

	.link-on-white {
		@apply font-semibold no-underline;
	}
</style>
