# Stato del servizio YSENS

Pagina pubblica dello stato della piattaforma YSENS di Y Digital: <https://ydigital-flavia.github.io/ysens-status/>
(diventerà `status.ysens.it`).

Costruita con [Upptime](https://upptime.js.org): GitHub Actions controlla ogni 5 minuti gli endpoint
pubblici di salute di PRODUZIONE (rispondono 503 quando un servizio è giù) e GitHub Pages pubblica la
pagina, fuori dai server di Y Digital. Il monitoraggio interno completo resta su UptimeRobot.

| Servizio sulla pagina | Endpoint |
|---|---|
| Portale YSENS | `health-app.ysens.it/health/ysens` |
| Ricezione dei dati dai dispositivi | `health-ingest.ysens.it/health/emqx` |
| Salvataggio delle misure | `health-ingest.ysens.it/health/influx_data` |
| Archivio delle misure | `health-analytics.ysens.it/health/influxdb` |
| Regole e avvisi | `health-analytics.ysens.it/health/rules` |

## Come si usa

- **Disservizio**: quando un servizio non risponde, Upptime apre da solo una issue (= incidente sulla
  pagina) e la chiude quando torna. Gli aggiornamenti per i clienti si scrivono come **commenti** alla issue:
  compaiono sulla pagina.
- **Incidente aperto a mano** (per esempio dati in ritardo con i servizi su): una issue con l'etichetta
  `status` e, nel testo, le parti coinvolte.
- **Manutenzione programmata**: una issue con l'etichetta `maintenance` e, nel testo, inizio e fine
  (formato in [documentazione Upptime](https://upptime.js.org/docs/scheduled-maintenance)).
  Va aperta almeno 5 giorni lavorativi prima (SLA).
- Configurazione in `.upptimerc.yml`; dopo una modifica parte da sola la ricostruzione del sito.

Gap ISO 27017 n. 31 (comunicazioni ai clienti). Cosa scrivere ai clienti e quando: wiki operativa,
«Avvisare i clienti».
