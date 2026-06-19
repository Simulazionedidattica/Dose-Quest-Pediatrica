# 🧸 Dose Quest Pediatrica

![Dose Quest](https://custom-icon-badges.demolab.com/badge/Dose%20Quest-Pediatrica-ff6aa7?style=for-the-badge&logo=heart&logoColor=white)
![Calcoli dosaggi](https://custom-icon-badges.demolab.com/badge/Calcoli-dosaggi-64c7ff?style=for-the-badge&logo=calculator&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google%20Fogli-invio%20automatico-34A853?style=for-the-badge&logo=googlesheets&logoColor=white)
![Mobile First](https://custom-icon-badges.demolab.com/badge/Mobile-first-bca8ff?style=for-the-badge&logo=device-mobile&logoColor=white)
![Infermieristica Pediatrica](https://custom-icon-badges.demolab.com/badge/Infermieristica-Pediatrica-50d3a2?style=for-the-badge&logo=shield-check&logoColor=white)

Quiz interattivo per studenti di **Infermieristica Pediatrica** sui calcoli dei dosaggi, organizzato come mini-simulazione a missioni.

## Link del quiz

Dopo la pubblicazione su GitHub Pages, il quiz sarà accessibile da:

```text
https://simulazionedidattica.github.io/Dose-Quest-Pediatrica/
```

## Funzioni principali

- 24 casi clinici pediatrici.
- Missioni divise in 4 livelli.
- Calcolatrice integrata nella schermata del caso.
- Autocontrollo della dose intermedia.
- Feedback immediato con micro-alert di sicurezza.
- Report finale con risposte corrette, percentuale e badge.
- Invio automatico dei risultati al Google Sheet della docente.
- CSV di backup.
- QR Code per accesso da cellulare.

## Badge finale dello studente

| Risultato | Badge |
|---|---|
| 22-24 corrette | 🛡️ Dose Guardian Pediatrico |
| 18-21 corrette | 🧮 Calcolatore sicuro |
| 14-17 corrette | 🌱 In formazione avanzata |
| meno di 14 | 📘 Ripasso guidato consigliato |

## File da caricare nella repository

Caricare nella root della repository:

```text
index.html
.nojekyll
README.md
```

## Collegamento Google Fogli

Il quiz è già configurato con questa Web App Apps Script:

```text
https://script.google.com/macros/s/AKfycbwQgIQdHmSTnOrsBc6fmpQxOexmdWt7cgaujnpgxqlC8rVwu2vwU-fJPjWciUnr4Gmtzw/exec
```

Quando lo studente clicca **Completa**, l'invio parte automaticamente.

## Icone Flaticon consigliate

Nel file HTML sono presenti icone provvisorie in stile emoji/sticker, così il quiz funziona subito senza dipendenze esterne.  
Se vuoi sostituirle con icone Flaticon, cerca e scarica in formato PNG/SVG queste categorie:

- `teddy bear`
- `medicine bottle`
- `syringe`
- `calculator`
- `nurse`
- `shield check`
- `clipboard medical`
- `baby bottle`
- `hospital bed`
- `star badge`

Poi puoi inserirle in una cartella:

```text
assets/icons/
```

E sostituire progressivamente le emoji nel file `index.html`.

## Esempi di badge personalizzati Markdown

Puoi aggiungere altri badge nel README usando **Custom Icon Badges** o **Shields.io**:

```markdown
![Dose Quest](https://custom-icon-badges.demolab.com/badge/Dose%20Quest-Pediatrica-ff6aa7?style=for-the-badge&logo=heart&logoColor=white)
![Calcolatrice](https://custom-icon-badges.demolab.com/badge/Calcolatrice-integrata-64c7ff?style=for-the-badge&logo=calculator&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google%20Fogli-report%20automatico-34A853?style=for-the-badge&logo=googlesheets&logoColor=white)
```

## Pubblicazione GitHub Pages

1. Aprire la repository `Dose-Quest-Pediatrica`.
2. Sostituire `index.html` con il nuovo file.
3. Caricare `.nojekyll` e `README.md`.
4. Fare **Commit changes**.
5. Attendere 1-3 minuti.
6. Aprire il link GitHub Pages e testare con `TEST Cristina`.
