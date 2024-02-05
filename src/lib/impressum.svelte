<script lang="ts">
	import { Modal, getModalStore } from '@skeletonlabs/skeleton';
	const modalStore = getModalStore();
</script>

{#if $modalStore[0]}
	<div class="w-modal-wide bg-white p-10 rounded-md space-y-2">
		<h2 class="h2">Impressum</h2>
		<p>
			Joël Foramitti arbeitet teilweise innerhalb seines
			Unternehmensgegenstandes angestellt über die smart@work GmbH und führt aus
			dieser Anstellung heraus die Aufträge auf Werkvertragsbasis aus.
			Ausführende*r des Auftrages/Werks ist also in diesem Fall Joël Foramitti,
			Werkvertragspartnerin für den Auftrag ist seine Arbeitgeberin die
			smart@work GmbH.
			<br /><br />
			Die smart@work GmbH hält, persönlich vertreten durch die Geschäftsführerin
			Angela Vadori, die notwendige Gewerbeberechtigung:
			<br />
			Standort der Gewerbeberechtigung: Gumpendorfer Straße 63B, 1060 Wien, Österreich
			<br />
			Unternehmensgegenstand: IT-Dienstleistungen & wissenschaftliche Arbeit
			<br />
			Kontaktdaten der Halterin der Gewerbeberechtigung: smart@work GmbH, Geschäftsführerin
			Angela Vadori, office@smartat.coop, +43 1 997 44 66
			<br />
			<br />UID Nr.: ATU75116919 FN 525600 t
			<br />Firmenbuchgericht: Handelsgericht Wien
			<br />Handelsrechtliche Geschäftsführung: Angela Vadori
			<br />Mitgliedschaften bei der Wirtschaftskammerorganisation: WKO
			<br />Anwendbare Rechtsvorschriften und Zugang dazu: Gewerbeordnung
			<br />Aufsichtsbehörde/Gewerbebehörde: Gewerbebehörde: Magistratisches
			Bezirksamt, 7., Hermanngasse 24-26
			<br />Angaben zur Online-Streitbeilegung: Verbraucher*innen haben die
			Möglichkeit, Beschwerden an die Online-Streitbeilegungsplattform der EU zu
			richten: http://ec.europa.eu/odr.
		</p>
	</div>
{/if}
