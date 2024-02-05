<script lang="ts">
	import { Modal, getModalStore } from '@skeletonlabs/skeleton';
	const modalStore = getModalStore();
</script>

{#if $modalStore[0]}
	<div class="w-modal-wide bg-white p-10 rounded-md space-y-2">
		<h2 class="h2">Datenschutz</h2>

		<p>
			Der Schutz Ihrer persönlichen Daten ist uns wichtig. Wir verarbeiten Ihre
			Daten auf Grundlage der geltenden gesetzlichen Bestimmungen (EU
			Datenschutz-Grundverordnung DSGVO, TKG 2003). In diesen
			Datenschutzinformationen informieren wir Sie über die wichtigsten Aspekte
			der Datenverarbeitung im Rahmen unserer Website.
		</p>

		<p>
			Die Nutzung unserer Webseite ist in der Regel ohne die Angabe
			personenbezogener Daten möglich. Sollten Sie, z.B. zum Zwecke der
			Kontaktaufnahme persönliche Daten eingeben, geben wir die notwendigen
			Informationen an Firmen weiter, die in unserem Auftrag Daten verarbeiten
			(z.B. unser Email und Cloud Anbieter). Wir beauftragen ausschließlich
			Firmen, die sich der EU Datenschutz-Grundverordnung unterwerfen.
		</p>
		<h3 class="h3">Server Protokolle</h3>
		<p>
			Der Server, von dem diese Webseite bereitgestellt wird, speichert
			Informationen die von Ihrem Browser automatisch an uns übermittelt werden,
			in sogenannten Log-Files. Diese Daten dienen der technischen Überwachung
			des Webservers. Sie beinhalten folgende Informationen: Browsertyp und
			Browserversion, Verwendetes Betriebssystem, Referrer URL (also die Seite,
			von der Sie zu uns gekommen sind), Die IP Adresse des zugreifenden
			Computers, Uhrzeit der Anfrage
		</p>

		<h3 class="h3">Verschlüsselte Übertragung</h3>

		<p>
			Diese Webseite nutzt aus Gründen der Sicherheit und des Datenschutzes eine
			SSL Verschlüsselung, die verhindert, dass Dritte die von Ihnen
			eingegebenen Daten auf dem Übertragungsweg abfangen und lesen können. Sie
			erkennen die aktive Verschlüsselung an dem grünen Vorhängeschloss oder
			ähnlichen Symbolen in der Adresszeile Ihres Browsers.
		</p>

		<h3 class="h3">Ihre Rechte</h3>

		<p>
			Ihnen stehen grundsätzlich die Rechte auf Auskunft, Berichtigung,
			Löschung, Einschränkung, Datenübertragbarkeit, Widerruf und Widerspruch
			zu. Wenn Sie glauben, dass die Verarbeitung Ihrer Daten gegen das
			Datenschutzrecht verstößt oder Ihre datenschutzrechtlichen Ansprüche sonst
			in einer Weise verletzt worden sind, können Sie sich bei der
			Aufsichtsbehörde beschweren. In Österreich ist dies die
			Datenschutzbehörde.
		</p>
	</div>
{/if}
