# Hjärt-MR Referensomvandlare

### [▶ Öppna verktyget](https://nethahussain.github.io/cardiac-mri-reference/)

**Hjärt-MR Referensomvandlare** — ett webbläsarbaserat kliniskt verktyg för radiologer som granskar hjärt-MR-undersökningar. Jämför ventrikelvolymer mot ålders- och könsspecifika referensvärden direkt i webbläsaren.

## Så fungerar det

1. Fyll i patientdata (kön, födelsedatum, vikt, längd)
2. Mata in uppmätta volymer från hjärt-MR (EDV, ESV, LV-massa) för vänster och höger kammare
3. Verktyget beräknar automatiskt:
   - **BSA** (Mostellers formel: √(vikt × längd / 3600))
   - **Slagvolym** (SV = EDV − ESV)
   - **Ejektionsfraktion** (EF = SV/EDV × 100 %)
   - **BSA-indexerade värden** (EDV/BSA, ESV/BSA, SV/BSA, LV-massa/BSA)
4. Varje indexerat värde jämförs med referensintervallet för patientens åldersdekad och kön
5. Resultaten färgkodas: **Normalt** (grönt), **Förhöjt** (rött), **Lågt** (orange)
6. En formaterad rapport kan kopieras till urklipp med en knapptryckning för inklistring i AGFA eller andra system

## Referensvärden

Ålders- och könsspecifika referensvärden för ålder 20–79:

| Kammare | Parametrar |
|---------|-----------|
| **Vänster kammare (LV)** | EDV/BSA, ESV/BSA, SV/BSA, EF, LV-massa/BSA |
| **Höger kammare (RV)** | EDV/BSA, ESV/BSA, SV/BSA, EF |

Referensdata baserad på **David Molnar, v.2025-05-02**.

## Användning

Ingen installation krävs. Öppna HTML-filen i valfri modern webbläsare.

### Alternativ A — Lokal fil
Ladda ner `index.html` och dubbelklicka för att öppna.

### Alternativ B — GitHub Pages
Öppna direkt via:
```
https://nethahussain.github.io/cardiac-mri-reference/
```

## Funktioner

- **En enda fil, inga beroenden** — allt körs i en självständig HTML-fil
- **Fungerar offline** — bara Google Fonts kräver internetanslutning (faller tillbaka till systemtypsnitt)
- **Direkt beräkning** — resultaten uppdateras i realtid medan du skriver
- **Visuella mätare** — se direkt var värdena hamnar i förhållande till normalintervallet
- **Kopiera rapport** — kopiera formaterad rapporttext till urklipp med ett klick
- **Flexibel datuminmatning** — skriv ÅÅÅÅMMDD eller ÅÅÅÅ-MM-DD
- **Responsiv** — fungerar på dator, surfplatta och mobil
- **Ingen patientdata sparas** — allt hanteras lokalt i webbläsaren, ingenting skickas till någon server

## XML-import från CVi42

Verktyget stöder import av XML-filer från CVi42, uppbyggt enligt samma princip som David Molnars originalimplementation.

## Workspace

Referensvärdena kan redigeras via Workspace (knappen uppe till höger). Ändrade värden sparas i webbläsarens localStorage och kan återställas till originalvärden.

## Krediter

- **Referensvärden**: David Molnar, v.2025-05-02
- **BSA-formel**: Mosteller (√(vikt × längd / 3600))
- **Originalverktyg**: Baserat på `MRI_Reference_Converter_Updated_20251108.xlsm` av David Molnar

## Kontakt

Vid eventuella fel i koden, kontakta: **nethahussain@gmail.com**

## Licens

Detta projekt är släppt under [CC0 1.0 Universal](LICENSE) — dedikerat till den publika domänen. Inga rättigheter förbehållna.
