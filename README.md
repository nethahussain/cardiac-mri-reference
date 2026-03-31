# Hjärt-MR Referensomvandlare

### [▶ Öppna verktyget](https://nethahussain.github.io/cardiac-mri-reference/)

**Hjärt-MR Referensomvandlare** — ett webbläsarbaserat kliniskt verktyg för radiologer som granskar hjärt-MR-undersökningar. Jämför ventrikelvolymer mot ålders- och könsspecifika referensvärden direkt i webbläsaren.

## Så fungerar det

1. Importera XML eller fyll i patientdata manuellt (kön, födelsedatum, vikt, längd)
2. Mata in uppmätta volymer från hjärt-MR (EDV, ESV, LV-massa) för vänster och höger kammare
3. Granska och redigera rapporten
4. Kopiera till urklipp med ett klick för inklistring i AGFA eller andra system

## Beräkningar

### 1. BSA (Body Surface Area) — Mostellers formel

```
BSA = √(vikt × längd / 3600)
```

Vikt i kg, längd i cm, resultat i m².
Exempel: 73 kg, 180 cm → √(73 × 180 / 3600) = √3.65 = **1.91 m²**

### 2. Ålder

```
Ålder = aktuellt år − födelseår
        (subtrahera 1 om födelsedagen inte inträffat ännu)
```

### 3. Åldersgrupp

Åldern mappas till en dekadgrupp: 20-29, 30-39, 40-49, 50-59, 60-69, 70-79. Ålder under 20 eller över 79: ingen referensgrupp tillgänglig.

### 4. Slagvolym (SV)

```
SV = EDV − ESV
```

Beräknas separat för vänster (LV) och höger (RV) kammare.

### 5. Ejektionsfraktion (EF)

```
EF = (SV / EDV) × 100 %
```

Dvs. ((EDV − ESV) / EDV) × 100. Anger andelen blod som pumpas ut per hjärtslag.

### 6. BSA-indexerade värden

Varje volym och massa divideras med BSA för att normalisera för kroppsstorlek:

| Parameter | Formel | Enhet |
|-----------|--------|-------|
| EDV/BSA | EDV ÷ BSA | ml/m² |
| ESV/BSA | ESV ÷ BSA | ml/m² |
| SV/BSA | SV ÷ BSA | ml/m² |
| LV mass/BSA | LV mass ÷ BSA | g/m² |

Dessa är värdena som jämförs mot referensintervallen.

### 7. Referensjämförelse

Varje BSA-indexerat värde jämförs med ett [min, max]-intervall baserat på patientens kön och åldersgrupp:

| Villkor | Status | Markering |
|---------|--------|-----------|
| värde < min | Lågt | * (asterisk) |
| min ≤ värde ≤ max | Normalt | Ingen |
| värde > max | Förhöjt | * (asterisk) |

### 8. Visuell mätare (gauge)

```
padding   = (max − min) × 0.35
gauge_min = min − padding
gauge_max = max + padding
position  = ((värde − gauge_min) / (gauge_max − gauge_min)) × 100%
```

Positionen begränsas till 0–100%. Det gröna området representerar normalintervallet.

## Referensvärden

Ålders- och könsspecifika referensvärden för ålder 20–79:

| Kammare | Parametrar |
|---------|-----------|
| **Vänster kammare (LV)** | EDV/BSA, ESV/BSA, SV/BSA, EF, LV-massa/BSA |
| **Höger kammare (RV)** | EDV/BSA, ESV/BSA, SV/BSA, EF |

## Användning

Ingen installation krävs. Öppna HTML-filen i valfri modern webbläsare.

### Alternativ A — Lokal fil (offline)
Ladda ner `index.html` och dubbelklicka för att öppna. Fungerar helt offline.

### Alternativ B — GitHub Pages
Öppna direkt via:
```
https://nethahussain.github.io/cardiac-mri-reference/
```

## Funktioner

- **En enda fil, inga beroenden** — allt körs i en självständig HTML-fil
- **Fungerar offline** — faller tillbaka till systemtypsnitt utan internet
- **Direkt beräkning** — resultaten uppdateras i realtid medan du skriver
- **XML-import** — dra och släpp XML-filer direkt i verktyget
- **Visuella mätare** — se direkt var värdena hamnar i förhållande till normalintervallet
- **Kopiera rapport** — kopiera formaterad rapporttext till urklipp med ett klick
- **Redigerbar rapport** — redigera rapporttexten innan kopiering
- **Avvikande värden markeras** — asterisk (*) vid värden utanför referensintervallet
- **Flexibel datuminmatning** — skriv ÅÅÅÅMMDD eller ÅÅÅÅ-MM-DD
- **Responsiv** — fungerar på dator, surfplatta och mobil
- **Ingen patientdata sparas** — allt hanteras lokalt i webbläsaren

## Workspace

Referensvärdena kan redigeras via Workspace (knappen uppe till höger). Ändrade värden sparas i webbläsarens localStorage och kan återställas till originalvärden.

## Kontakt

Vid eventuella fel i koden, kontakta: **Netha Hussain netha.hussain@vgregion.se**

## Licens

Detta projekt är släppt under [CC0 1.0 Universal](LICENSE) — dedikerat till den publika domänen. Inga rättigheter förbehållna.
