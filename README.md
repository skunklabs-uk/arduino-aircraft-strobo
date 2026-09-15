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

Il report non esegue firmware, build o installazioni. La preview browser del
simulatore HTML resta un gate applicabile e non completato; non è stata usata
la prova Node con timer sostituiti come evidenza browser o di timing reale.

Per il protocollo del collegamento, consultare il [runbook Developer
Workspace](https://github.com/skunklabs-uk/developer-workspace/blob/main/docs/WORKSPACE-HANDOFF.md).
