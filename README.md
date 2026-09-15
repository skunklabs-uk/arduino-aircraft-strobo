# Strobo firmware for arduino

Emulate the boeing flashing sequence on an aurduino strobo lights using the interrupt function

2 modes available
- Flight mode
- Landing mode

# Files

- strobo.c - source code for aurduino
- strobo.html - flash programming emulator

## Modalità e simulatore

Il firmware in `strobo.c` implementa due modalità: Flight e Landing. Il
simulatore browser in `strobo.html` riproduce invece tre modalità: Flight,
Landing ed Emergency. Nel simulatore il tasto `P`/`p` passa alla modalità
successiva. Questa differenza riguarda il simulatore; non dimostra la fedeltà
all'hardware, il corretto funzionamento del firmware o la precisione dei tempi.

## Collegamento seriale con Developer Workspace

Per [Homelab #1265](https://github.com/skunklabs-uk/homelab/issues/1265), il
collegamento usa un incarico vincolato a repository e thread, branch/head dello
snapshot e prompt versionato. Il consumer lavora in modo seriale e il child
restituisce un report; il coordinatore verifica il risultato e registra il
`RETURN`. Eventuale applicazione della proposta e merge restano passaggi del
parent su una normale PR. Lo snapshot senza parent non viene integrato.

Il report non ha eseguito firmware, build o installazioni. La successiva
verifica browser del simulatore è descritta sotto; la prova Node con timer
sostituiti non è stata usata come evidenza browser o di timing reale.

Per il protocollo del collegamento, consultare il [runbook Developer
Workspace](https://github.com/skunklabs-uk/developer-workspace/blob/main/docs/WORKSPACE-HANDOFF.md).

## Verifica della preview HTML

Il [producer del 15 settembre 2026](https://github.com/skunklabs-uk/arduino-aircraft-strobo/actions/runs/34996543485),
sul commit `9c9c7264425c19b62d688c2867d4bfb11d97ba2c`, ha costruito e
pubblicato la stessa immagine verificata via HTTP, confrontando HTML e LICENSE
byte per byte. Il grant runner temporaneo è stato ritirato.

Il [rollout GitOps Homelab #1309](https://github.com/skunklabs-uk/homelab/pull/1309)
ha usato quell'artifact tramite Harbor, con Pod Ready, digest verificato e
`hostUsers: false`. La route risultava Accepted/ResolvedRefs; l'accesso anonimo
riceveva il redirect 302 di Cloudflare Access. Queste sono prove del rollout
temporaneo, non una promessa di disponibilità permanente dell'URL.

In Chrome reale su Windows sono stati osservati i programmi 0 Flight,
1 Landing e 2 Emergency, il passaggio con `P`/`p`, il ritorno al programma 0
e le variazioni visive delle luci. L'ultimo run non ha registrato eventi di
errore. Le prove e gli screenshot sono raccolti nella
[missione Homelab #1265](https://github.com/skunklabs-uk/homelab/issues/1265).

La prova mobile usa l'emulazione Chrome a 390 pixel: la pagina conserva un
viewport CSS di 980 pixel e non è responsive. Non sono stati verificati
comandi touch, hardware Arduino, firmware o precisione dei tempi di lampeggio.

Il ritiro autorizzato è completato: Application e namespace risultano
assenti dopo la [PR Homelab #1311](https://github.com/skunklabs-uk/homelab/pull/1311).
DNS, Access e il solo ingresso tunnel temporaneo sono stati rimossi;
lo state OpenTofu e le fonti operative sono aggiornati. Il workflow,
Dockerfile e ignore temporanei sono ritirati; artifact e prove sono
conservati. Il branch temporaneo segue il lifecycle della PR di closeout.
L’utente è stato avvisato prima del teardown. Il
[README runtime Homelab](https://github.com/skunklabs-uk/homelab/blob/main/gitops/apps/developer-workspace/README.md)
resta il riferimento per il collegamento seriale.
