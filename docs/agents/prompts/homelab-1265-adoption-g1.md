# Homelab #1265 — adozione Arduino Aircraft Strobo

**Stato: Active**

## Incarico e autorità

Per [Homelab #1265](https://github.com/skunklabs-uk/homelab/issues/1265), prepara un report-only con proposta README italiana che distingua firmware e simulatore HTML. Leggi integralmente la RFC corrente fornita dal parent, AGENTS.md e i cinque input qualificati sotto. Non modificare file, pubblicare, creare commit o eseguire firmware, build, installazioni o rete.

## Input qualificati

Source `0301e0f6ede67a0c8ac503f1ac384d3b6553f397`. Snapshot assegnato: branch/head esatti nella richiesta; non confonderli con il source. File ammessi: AGENTS.md, README.md, LICENSE, strobo.c, strobo.html e questo prompt. Nessun altro contenuto o fonte remota. Lo snapshot senza parent non sarà mai integrato: la proposta viene applicata dal parent su una normale PR discendente dal source.

## Delta utile

Il README elenca due modalità senza distinguere i due file. Il firmware contiene Flight e Landing; il simulatore HTML contiene Flight, Landing ed Emergency e usa P/p per cambiarle. Descrivi questa differenza, i file e l'uso del simulatore senza affermare fedeltà hardware, precisione temporale o corretto funzionamento del firmware. Preserva la licenza e non modificare timing, GPIO, callback, grafica o comportamento. Non ampliare il task a una correzione del firmware.

Aggiungi soltanto una breve nota sull'adozione: incarico vincolato a repository/thread e branch/head, consumer seriale, report, verifica e RETURN del coordinatore, eventuale applicazione e merge parent. Rimanda al [runbook](https://github.com/skunklabs-uk/developer-workspace/blob/main/docs/WORKSPACE-HANDOFF.md) senza duplicare protocollo o introdurre nuovi obblighi. Non attestare risultati runtime prima della verifica parent.

## Verifiche e limiti

Sono ammesse letture e confronto testuale locale. Il parent ha osservato con un harness Node VM e timer sostituiti da callback immediate il ciclo P/p 0→1→2→0, etichette e tasto estraneo ignorato. Non è un browser, non misura tempi reali e non verifica hardware. Non riportare questa prova come collaudo browser o firmware.

La preview HTTP non è pertinente al firmware; è invece pertinente al simulatore HTML. Il report documentale non completa l'adozione del repository finché artifact producer e preview Kubernetes-native con browser restano da verificare. Non classificare l'intero progetto NON APPLICABILE. Board/toolchain e flash non sono autorizzati né necessari alla proposta README.

## Consegna

Report italiano autosufficiente con source/snapshot esaminati, fonti effettivamente usate, proposta README minima, verifiche e limiti. Rivedi tecnicamente e con humanize-writing se disponibile, senza installazioni o falsa review indipendente. Distingui report delivered, accettazione RETURN e applicazione/merge parent. Non inventare prove o URL. Il parent ritira prompt e snapshot dopo la consegna verificata e preserva stato e storico; la missione resta aperta per le prove applicative mancanti.
