# OpenTelemetry Astronomy Shop Labs
## Elastic Observability Workshop

Deze labreeks gebruikt de **OpenTelemetry Astronomy Shop** als demonstratieapplicatie en **Elastic Observability** voor het analyseren van metrics, logs en traces.

De labs zijn opgebouwd volgens een incident-gedreven aanpak. Iedere oefening simuleert een realistische productieomgeving waarin deelnemers observability gebruiken om problemen te analyseren en op te lossen.

<img width="3820" height="2170" alt="image" src="https://github.com/user-attachments/assets/0f4e175f-cefa-472f-9ca9-1db806d0b9e5" />

---

# Lab 1 – Kennismaken met de Astronomy Shop

## Doel

De architectuur en telemetry van de Astronomy Shop leren kennen.

## Leerdoelen

- Services identificeren
- Begrijpen hoe telemetry is opgebouwd
- Navigeren binnen Elastic Observability

## Opdrachten

- Open de Service Map.
- Hoeveel services zijn aanwezig?
- Welke services zijn publiek bereikbaar?
- Welke databases worden gebruikt?
- Zoek een complete checkout trace.

## Resultaat

De deelnemer begrijpt:

- Services
- Traces
- Metrics
- Logs

---

# Lab 2 – End-to-End Trace Analysis

## Scenario

Een klant meldt dat het plaatsen van een bestelling erg langzaam verloopt.

## Opdracht

Zoek een trace met een totale responstijd van meer dan 3 seconden.

Beantwoord de volgende vragen:

- Welke service veroorzaakt de meeste vertraging?
- Welke span duurt het langst?
- Hoeveel downstream calls worden uitgevoerd?
- Is de vertraging gerelateerd aan CPU, netwerk of database?

## Elastic onderdelen

- APM
- Waterfall View
- Span Attributes
- Trace Timeline

---

# Lab 3 – Service Dependency Analysis

## Scenario

Je bent nieuw in het platformteam.

Niemand beschikt over een actuele architectuurtekening.

## Opdracht

Maak zelf een architectuurdiagram met uitsluitend:

- Service Map
- Distributed Traces

Beschrijf de relaties tussen:

- frontend
- checkout
- payment
- recommendation
- shipping
- accounting
- cart
- inventory

## Extra opdracht

- Welke services zijn bedrijfskritisch?
- Welke services vormen een Single Point of Failure?

---

# Lab 4 – Metrics Investigation

## Scenario

De CPU-belasting neemt plotseling toe.

## Opdracht

Gebruik de Metrics-app om de oorzaak te onderzoeken.

Analyseer:

- CPU
- Memory
- Request Rate
- Error Rate
- Latency

## Resultaat

Schrijf een korte conclusie over de mogelijke oorzaak.

---

# Lab 5 – Logs en Traces Correlatie

## Scenario

Tijdens het afrekenen ontvangen gebruikers foutmeldingen.

## Opdracht

Gebruik uitsluitend:

- Trace ID
- Logs

Zoek:

- Exception
- Stacktrace
- Oorzaak van de fout

---

# Lab 6 – Root Cause Analysis

## Scenario

Gebruikers melden:

> "De webshop is erg langzaam."

Je ontvangt alleen:

> Ticket #4587

Verder is geen aanvullende informatie beschikbaar.

## Opdracht

Gebruik:

- Metrics
- Logs
- Traces

Bepaal:

- Root Cause
- Impact
- Mogelijke oplossing

---

# Lab 7 – Distributed Tracing Deep Dive

## Doel

Diepgaand inzicht verkrijgen in OpenTelemetry tracing.

## Onderwerpen

- Parent Span
- Child Span
- Span Links
- Attributes
- Events
- Status Codes

## Opdracht

Teken de volledige trace van een checkout-transactie.

Geef aan:

- Welke spans synchroon verlopen
- Welke spans parallel worden uitgevoerd
- Waar de meeste tijd verloren gaat

---

# Lab 8 – Service Level Objectives (SLO)

## Scenario

Voor de Checkout API moet een SLO worden opgesteld.

## Opdracht

Definieer:

**SLO**

- 99% van alle requests moet sneller zijn dan 500 ms.

Maak vervolgens:

- SLI
- Error Budget
- Burn Rate

Gebruik hiervoor Elastic SLO's.

---

# Lab 9 – Alerting

## Opdracht

Configureer alerts voor:

- Hoge latency
- Hoge error rate
- Pod restart
- Memory leak

## Extra

Genereer testverkeer en controleer of de alerts correct afgaan.

---

# Lab 10 – Kubernetes Observability

## Opdracht

Onderzoek de Kubernetes-omgeving.

Analyseer:

- Pods
- Nodes
- Containers

Zoek naar:

- Restart loops
- CPU throttling
- OOMKilled containers

---

# Lab 11 – OpenTelemetry Collector

## Doel

Inzicht krijgen in de telemetry-pipeline.

```
Astronomy Shop
      │
      ▼
OpenTelemetry Collector
      │
      ▼
Elastic Observability
```

## Opdracht

Onderzoek de configuratie van de Collector.

Experimenteer met:

- Processors
- Batching
- Sampling
- Filtering
- Resource Attributes

---

# Lab 12 – OpenTelemetry Semantic Conventions

## Opdracht

Bekijk telemetry van:

- HTTP requests
- Database calls
- Messaging

Controleer:

- Welke attributes aanwezig zijn
- Welke verplichte semantic conventions ontbreken
- Welke metadata verbeterd kan worden

---

# Lab 13 – High Cardinality

## Scenario

De opslagkosten in Elastic lopen sterk op.

## Opdracht

Onderzoek:

- Labels
- Resource Attributes
- Metric Dimensions

Zoek bronnen van:

- High Cardinality
- Onnodige labels
- Kostbare metrics

## Extra

Doe voorstellen om opslagkosten te verlagen.

---

# Lab 14 – Performance Tuning

## Opdracht

Optimaliseer de telemetry-pipeline.

Experimenteer met:

- Sampling
- Histograms
- Export intervals
- Batch Processor

Vergelijk:

- Opslaggebruik
- Datavolume
- Query-performance

---

# Lab 15 – Observability Maturity Challenge

## Capstone

Duur: 2 tot 3 uur.

Je ontvangt uitsluitend:

- Een storing
- Een dashboard
- Toegang tot Elastic Observability

De oorzaak is onbekend.

Mogelijke incidenten:

- Payment timeout
- Inventory service down
- Kafka backlog
- DNS-probleem
- Hoge GC-tijden
- Database latency
- Memory leak
- Verlopen certificaat
- Overbelaste OpenTelemetry Collector

## Eindopdracht

Lever een volledige Root Cause Analysis (RCA) op.

Beschrijf:

- Tijdlijn van het incident
- Bewijs uit metrics
- Bewijs uit logs
- Bewijs uit traces
- Root Cause
- Herstelactie
- Aanbevelingen ter voorkoming van herhaling

---

# Leerdoelen van de complete workshop

Na afloop kunnen deelnemers:

- Navigeren binnen Elastic Observability
- Distributed traces analyseren
- Metrics interpreteren
- Logs correleren met traces
- Root Cause Analyses uitvoeren
- Kubernetes-problemen onderzoeken
- OpenTelemetry Collectors configureren
- Semantic Conventions toepassen
- High Cardinality herkennen
- Telemetry optimaliseren
- SLO's en alerts implementeren
- Productie-incidenten zelfstandig oplossen
