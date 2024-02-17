<script lang="ts">
	import Icon from '@iconify/svelte';
	import { initializeStores } from '@skeletonlabs/skeleton';
	import { Modal, getModalStore } from '@skeletonlabs/skeleton';
	import type {
		ModalSettings,
		ModalComponent,
		ModalStore
	} from '@skeletonlabs/skeleton';

	import Impressum from '$lib/impressum.svelte';
	import Privacy from '$lib/privacy.svelte';

	const modalRegistry: Record<string, ModalComponent> = {
		Impressum: { ref: Impressum },
		Privacy: { ref: Privacy }
	};
	initializeStores();
	const modalStore = getModalStore();
	const impressum: ModalSettings = {
		type: 'component',
		component: 'Impressum'
	};
	const privacy: ModalSettings = {
		type: 'component',
		component: 'Privacy'
	};

	const icons = [
		{
			name: 'Email',
			label: 'joel@foramitti.org',
			href: 'mailto:joel@foramitti.org',
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
			tags: ['Open-Source', 'Partizipation', 'Datenbank'],
			subtitle:
				'Open-Source Plattform für Partizipation, Kommunikation und Datenverwaltung'
		},
		{
			href: 'https://augustin.or.at/mit-bargeld-oder-karte/',
			title: 'Augustina',
			date: '2023',
			tags: ['Open-Source'],
			subtitle:
				'Open-Source System für bargeldloses Bezahlen von Straßenzeitungen'
		},
		{
			href: 'https://agentpy.readthedocs.io/en/latest/',
			title: 'AgentPy',
			date: '2021',
			subtitle:
				'Open-Source Paket für die Simulation von agenten-basierten Modellen'
		}
	];
</script>

<Modal components={modalRegistry} />

<div class="h-full mx-auto flex justify-center items-center">
	<div class="space-y-10 sm:space-y-20 max-w-5xl w-full p-10 md:p-24 lg:mt-35">
		<div
			id="pf-title"
			class="flex flex-row gap-5 md:gap-10 items-center justify-between"
		>
			<div class="w-2/3">
				<h1 class="h1 mb-2">Joël Foramitti</h1>
				<p class="text-xl md:text-2xl italic mb-4">
					Wissen und Werkzeuge für kooperatives Wirtschaften
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

			<!-- <div class="">
				<a href="mailto:joel@foramitti.org">
					<button type="button" class="btn font-bold pf-box">
						<Icon icon="bi:envelope-at-fill" class="mr-2" /> Kontakt aufnehmen
					</button>
				</a>
			</div> -->
		</div>

		<div id="pf-cv" class="space-y-6">
			<h2 class="h2">Hintergrund</h2>
			<ul class="list-inside list-disc text-md pf-box p-5">
				<li>
					<span class="font-bold">02.2024 - heute</span>: Selbstständig,
					Wirtschaftsforscher & Software-Entwickler
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

		<div id="pf-services" class="space-y-6">
			<h2 class="h2">Angebote</h2>

			<div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
				<div class="pf-box w-full px-6 py-5 space-y-2">
					<h3 class="h3">Software-Entwicklung</h3>
					<p class="text-md">
						Ich biete
						<a href="#projects" class="link-on-white"
							>maßgeschneiderte Lösungen</a
						>
						für Datenbanksysteme und digitale Plattformen mit einem Fokus auf Open-Source
						Technologien.
					</p>
					<p class="text-md">
						Dabei begleite ich den gesamten Entwicklungs-Prozess von der
						gemeinsamen Konzeption bis zur Umsetzung und langfristigen Wartung.
					</p>
				</div>

				<div class="pf-box w-full px-6 py-5 space-y-2">
					<h3 class="h3">Forschung & Beratung</h3>
					<p>
						Ich biete Unterstützung bei der Entwicklung von Prozessen und
						Strukturen für Partizipation und Selbstorganisation.
					</p>
					<p>
						Dabei verbinde ich meinen wissenschaftlichen Hintergrund mit
						praktischer Erfahrungen aus <a
							href="#partners"
							class="link-on-white">kooperativen Wirtschaftsprojekten</a
						>.
					</p>
				</div>
			</div>
		</div>

		<div id="pf-services" class="space-y-6">
			<h2 class="h2">Kollektive</h2>
			<div
				id="partners"
				class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5"
			>
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

		<div id="projects" class="space-y-6">
			<h2 class="h2">Referenzen</h2>

			<div
				id="projects"
				class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5"
			>
				{#each projects as { title, subtitle, date, href }}
					<a {href} target="_blank">
						<div class="pf-box h-full px-6 py-5 space-y-2">
							<div class="flex flex-col space-y-2 m-1">
								<h3 class="h3">{title}</h3>
								<p class="text-sm italic">{date}</p>
								<p>{subtitle}</p>
							</div>
						</div>
					</a>
				{/each}
			</div>
		</div>
		<div>
			<a href="mailto:joel@foramitti.org">
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
				<span class="font-semibold">Joël Foramitti</span>
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
					on:click={() => modalStore.trigger(impressum)}
				>
					Impressum
				</button>
				<button
					class="link-on-white"
					on:click={() => modalStore.trigger(privacy)}
				>
					Datenschutz
				</button>
			</div>
		</div>
	</div>
</div>

<style lang="postcss">
	.pf-box {
		@apply bg-white/60 hover:bg-white duration-150 drop-shadow-sm rounded-md text-black;
	}

	.link-on-white {
		@apply no-underline font-semibold text-primary-900;
		color: --theme-font-color-base;
	}
</style>
