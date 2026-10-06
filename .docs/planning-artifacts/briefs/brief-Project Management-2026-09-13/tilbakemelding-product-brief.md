# Tilbakemelding på product brief

| | |
|---|---|
| **Gruppe** | G54 – G54-pedersen |
| **Product brief** | `.docs/planning-artifacts/briefs/brief-Project Management-2026-09-13/brief.md` (commit `f212b94`) |
| **Tilbakemelding fra** | Faglærer i IBE160 (utarbeidet med KI-støtte) |
| **Dato** | 2026-10-06 |

## Samlet vurdering

- **Bør revideres før dere går videre.** Rett punktene markert «Endre» før dere lager PRD og arkitektur.

**Det som er bra:**

1. Produktideen har en tydelig og original kjerne: «everything is a task», med uendelig nesting og blokkering som et flagg oppå status i stedet for en egen status. Det er et klart designvalg som er lett å forklare og kan begrunnes godt.
2. Problemet er beskrevet med en gjenkjennelig situasjon (utvikleren som leter etter riktig prosjekt, story og board i ti minutter), og løsningsdelen beskriver hva brukeren ser og gjør, ikke teknologi.
3. KI-bruken er avgrenset og kontrollert: forslag til deloppgaver og beskrivelser blir ikke brukt før brukeren sier ja, og den daglige oppsummeringen er et forslag, ikke en instruks.

**De viktigste endringene:**

1. **Omfanget er for stort for v1.** Scope «In» inneholder full oppgavemodell, aktivitetsfeed med kommentarer, timeføring, lydopptak og beskrivelseshistorikk, tre ulike visninger med dra-og-slipp, varsler ved blokkering, nevnelser, to KI-funksjoner og en selvlærende onboarding-oppgave. Det er minst fem store funksjonsområder. Velg oppgavetreet med blokkering som kjerne, og flytt resten til senere trinn.
2. **Suksesskriteriene kan ikke testes i emnet.** «Blocked tasks get resolved faster», «no Slack archaeology» og «new team members are productive within their first day» krever et ekte team over tid. Legg til funksjonelle kriterier, for eksempel «når en oppgave markeres som blokkert med begrunnelse, får den ansvarlige et varsel og ser hvilke oppgaver som venter».
3. **Avklar brukere og innlogging.** Briefen forutsetter et team med flere brukere, varsler og en teamoversikt, men sier ikke noe om innlogging, roller eller hvordan et team opprettes. Skriv inn hvem som kan gjøre hva, og om prosjektlederen har andre rettigheter enn teammedlemmene.

## Vanskelighetsgrad og gjennomførbarhet

### Vurdert vanskelighetsgrad

- **Middels**

**Sammenlignbart med:** 6) To-do-liste med smarte etiketter (enkel) i grunnen, men flere brukere, varsler, flere visninger og to KI-funksjoner løfter prosjektet til nivået for 2) AI CV- og søknadsassistent (middels). Med hele Scope «In» slik den står nå, er arbeidsmengden nærmere et vanskelig prosjekt, selv om reglene i seg selv er forståelige.

**Begrunnelse:**

| Faktor | Nivå (lav / middels / høy) | Kommentar |
|---|---|---|
| Domenelogikk – hvor mange og hvor kompliserte regler og beregninger må stemme? | middels | Nesting, statusregler, blokkering som påvirker andre oppgaver, fristfarge og «done hidden by default». Reglene er forståelige, men samspillet i et tre er lett å gjøre feil i. |
| Datamodell – antall entiteter og relasjoner mellom dem | middels | Oppgave med forelder–barn-relasjon i vilkårlig dybde, blokkeringsrelasjoner mellom oppgaver, brukere, team, aktivitetshendelser og lydfiler. Trestrukturer i en database krever bevisste valg. |
| Brukere, roller og innlogging | middels | Teammedlemmer og prosjektleder, nevnelser og varsler. Innlogging er ikke nevnt, men er nødvendig. |
| KI-funksjonalitet i appen, f.eks. kall til språkmodell, prompts i koden og håndtering av usikre svar | middels | To funksjoner: redigering med bekreftelse og en daglig oppsummering basert på feed-data. Oppsummeringen krever en tidsstyrt jobb eller generering ved innlogging. |
| Integrasjoner og eksterne tjenester, f.eks. API-er, betaling og e-post | lav | Bare et LLM-API. E-postvarsler er bevisst holdt utenfor. |
| Sanntid, samtidighet eller flere brukere som påvirker hverandre | middels | Flere brukere endrer de samme oppgavene, varsler og blokkeringer påvirker andre. Sanntid er ikke krevd, men brukerne vil forvente oppdaterte visninger. |
| Filhåndtering, f.eks. opplasting, PDF-lesing og eksport | middels | Lydopptak i nettleseren, lagring og avspilling er en egen teknisk oppgave. |
| Sikkerhet og personvern | middels | Timeføring og «how long tasks have been sitting» per person kan oppleves som overvåking. Det er verdt å reflektere over. |

**Hva vanskelighetsgraden betyr for dere:**

- _Middels:_ Et godt balansert valg. Pass på at kjerneflyten blir ferdig og stabil før dere legger til mer. For dere betyr det oppgavetre, blokkering og aktivitetsfeed med kommentarer før visningene, lydopptak og KI-oppsummeringen.

### Gjennomførbarhet med BMAD og Claude Code

Dere skal planlegge med BMAD (product brief → PRD → arkitektur → epics og stories) og implementere med Claude Code. Vurderingen under tar hensyn til at det må være tid til hele denne flyten, og til testing, retting og README til slutt.

| Spørsmål | Vurdering (OK / risiko / stor risiko) | Kommentar |
|---|---|---|
| **Tid og omfang** – kan v1 realistisk bli ferdig og stabil i løpet av semesteret, med tid til flere iterasjoner? | stor risiko | Med hele Scope «In» blir det mange halvferdige funksjoner. Med kjernen (oppgavetre, blokkering, feed, én visning og én KI-funksjon) er det realistisk. |
| **BMAD-flyten** – er briefen konkret nok til at PRD, arkitektur og stories kan lages uten store hull, og blir det overkommelig mange stories? | risiko | Funksjonene er godt beskrevet, men innlogging, team og roller mangler. Med alle funksjonene blir det mange stories. |
| **Egnet for Claude Code** – bruker løsningen en vanlig, godt dokumentert teknologistakk som Claude Code håndterer godt, eller krever den nisjeteknologi, spesialmaskinvare eller mye manuell konfigurasjon? | OK | En vanlig webstakk med database passer godt. Lydopptak og dra-og-slipp har gode, dokumenterte biblioteker. |
| **Kontroll på KI-ens arbeid** – kan gruppen selv avgjøre om koden gjør det riktige? Krever domenet kunnskap gruppen ikke har, f.eks. avanserte beregninger eller fagregler, så er det vanskelig å kvalitetssikre. | OK | Dere kjenner domenet (prosjektverktøy) godt og kan selv vurdere om oppførselen er riktig. |
| **Testbarhet** – finnes det tydelige regler og forventede resultater som tester kan skrives mot? | risiko | Det finnes mange gode testbare regler (nesting, blokkering, fristfarge, skjulte ferdige oppgaver), men suksesskriteriene i briefen er ikke testbare. |
| **Kjørbar for sensor** – kan appen kjøres lokalt etter README, uten gruppens nøkler, betalte kontoer eller egen infrastruktur? | risiko | KI-funksjonene krever en LLM-nøkkel. Planlegg at resten av appen fungerer uten, og lag testbrukere og et ferdig eksempelteam. |
| **Avhengigheter og kostnader** – krever løsningen betalte API-er, f.eks. språkmodeller, og finnes det en plan for kostnad, testmodus eller mock-data? | risiko | Den daglige oppsummeringen for hver bruker gir mange kall. Planlegg generering ved behov og lagrede eksempelsvar for testing. |

**Konklusjon om gjennomførbarhet:**

- **Gjennomførbart med justert omfang.** Se forslagene under.

**Forslag til justering av omfang eller vanskelighetsgrad:**

1. **V1:** innlogging og ett team, oppgavetre med nesting, status, prioritet og blokkering med begrunnelse og varsel i appen, aktivitetsfeed med kommentarer, oppgavetreet som visning og KI-assistert redigering med bekreftelse.
2. **Senere trinn, i prioritert rekkefølge:** teamoversikt, bucket-visning med dra-og-slipp, timeføring, daglig KI-oppsummering, lydkommentarer og onboarding-oppgave. Skriv rekkefølgen inn i briefen.

## Hvorfor product brief er viktig for mappen

Product brief er utgangspunktet for PRD, arkitektur, stories og til slutt koden. Del 1 av mappen vurderes blant annet på om sensor kan følge en sporbar vei fra plan til ferdig app. Den vurderes også på om appen gjør det dere har beskrevet, om den er testet, om den er godt designet, og om den kan kjøres etter README. Et uklart, for stort eller for lite brief gjør alt dette vanskeligere senere. Det er mye enklere å rette nå enn sent i semesteret.

## 1. Gjennomgang av briefens deler

| Del av brief | Status | Kommentar |
|---|---|---|
| Executive Summary – er det klart hva appen er, og hvilket problem den løser? | OK | Tydelig: et prosjektverktøy for mindre organisasjoner bygd rundt ett begrep, oppgaven. |
| The Problem – er problemet konkret, med reelle situasjoner og brukere? | OK | Gjenkjennelig og godt formulert. Eksemplene på Jira og Slack gjør problemet konkret. |
| The Solution – beskriver løsningen brukeropplevelsen, ikke bare teknologi? | OK | Svært godt beskrevet fra brukerens side, med tre visninger og konkrete funksjoner. |
| What Makes This Different – er vurderingen ærlig og realistisk? | Juster | Punktene er tydelige, men konkurrenter som allerede har nestede oppgaver og blokkering bør nevnes, slik at det blir tydelig hva som faktisk er nytt. |
| Who This Serves – er primærbrukerne tydelige, og vet vi hva de trenger? | Juster | To grupper (teammedlemmer og prosjektledere). Velg én primærbruker å designe kjerneflyten for, og beskriv størrelsen på et typisk team. |
| Success Criteria – kan kriteriene faktisk sjekkes eller testes? | Endre | Alle kriteriene krever et ekte team over tid. Legg til funksjonelle kriterier som kan bli testtilfeller. |
| Scope – er det klart hva som er med i første versjon, og hva som ikke er det? | Endre | «Out» er tydelig, men «In» inneholder alt som er beskrevet i løsningen. Del opp i v1 og senere trinn. |
| Vision – henger visjonen sammen med resten uten å blåse opp omfanget? | OK | Kort og konsistent med ett-begrep-filosofien. |

## 2. Utgangspunkt for del 1 av mappen

Punktene følger kriteriene i sensorveiledningen for del 1. Vektene i parentes viser hvor mye hvert kriterium teller i del 1.

| Kriterium i del 1 | Hva briefen bør legge til rette for | Status | Kommentar |
|---|---|---|---|
| **1. Prosess og KI-styring** (30 %) | Brief som er presis nok til at PRD og stories kan bygges direkte på den, slik at krav kan spores fra brief til kode. | Juster | Briefen er laget med BMAD og ligger ryddig. Etter én commit har det ikke skjedd mer. Kom i gang med PRD, og commit jevnlig. |
| **2. Funksjonalitet og omfang** (20 %) | Realistisk omfang for gruppen og semesteret: en tydelig kjerneflyt som kan bli ferdig og stabil, og nok innhold til å vise reell funksjonalitet. | Endre | Kjernen er tydelig, men omfanget er for stort. Velg v1 som foreslått. |
| **3. Kvalitetssikring og testing** (15 %) | Suksesskriterier og funksjoner som er konkrete nok til å bli testtilfeller. | Endre | Skriv reglene for nesting, blokkering og fristfarge som testbare krav. Gjør suksesskriteriene funksjonelle. |
| **4. Design og brukeropplevelse** (10 %) | Tydelige brukere og brukssituasjoner som designet kan bygges rundt, gjerne med de viktigste skjermbildene eller flytene skissert. | OK | Visningene og «visual health» med fristgradient gir et godt utgangspunkt for design. Husk at status ikke bare kan vises med farge. |
| **5. Kodekvalitet og arkitektur** (10 %) | Teknologivalg som er begrunnet og ikke mer komplekse enn appen trenger. | Juster | Ingen teknologi er valgt ennå. Trestrukturen og blokkeringsrelasjonene bør være et bevisst arkitekturvalg, siden de påvirker hele appen. |
| **6. README og kjørbarhet** (10 %) | Løsning som andre kan kjøre lokalt uten betalte kontoer, og uten tilgang til gruppens egne tjenester og nøkler. | Juster | Planlegg testbrukere, et eksempelteam med oppgaver og at appen fungerer uten LLM-nøkkel. |
| **7. Ryddighet i repoet** (5 %) | En plan for hvor hemmeligheter, testdata og dokumentasjon skal ligge. | Juster | Mappenavnet `brief-Project Management-2026-09-13` inneholder mellomrom, som kan skape problemer i kommandoer. Planlegg `.env.example` og hvor opplastede lydfiler skal lagres (ikke i Git). |

## 3. Neste steg for gruppen

1. Del Scope i v1 og senere trinn som foreslått, og skriv det inn i briefen.
2. Legg til innlogging, team og roller i briefen, og skriv 6–8 funksjonelle suksesskriterier i formen «en bruker kan …».
3. Lag PRD-en, og beskriv der reglene for nesting og blokkering så presist at de kan bli de første automatiske testene.

Oppdater product brief i repoet når dere har gjort endringene, slik at historikken viser hvordan planen utviklet seg. Det er en del av prosessen sensor ser etter.
