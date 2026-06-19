/**
 * Dose Quest Pediatrico - ricezione risultati su Google Fogli.
 * Versione configurata per il foglio della docente:
 * https://docs.google.com/spreadsheets/d/1OsY6cpXVk7VywmXbyi8Y8QiMQK9FNNx_2Z0P-N7_2so/edit
 *
 * ISTRUZIONI RAPIDE
 * 1) Apri il foglio Google dei risultati.
 * 2) Estensioni > Apps Script.
 * 3) Cancella tutto in Code.gs e incolla questo codice.
 * 4) Salva.
 * 5) Dal menu delle funzioni scegli setup e clicca Esegui: autorizza lo script.
 * 6) Distribuisci > Nuova distribuzione > App web.
 *    - Esegui come: Me
 *    - Chi ha accesso: Chiunque abbia il link / Chiunque
 * 7) Copia l'URL che termina con /exec e incollalo nel quiz.
 */

const SPREADSHEET_ID = '1OsY6cpXVk7VywmXbyi8Y8QiMQK9FNNx_2Z0P-N7_2so';
const SHEET_RISULTATI = 'Risultati Quiz';
const SHEET_DETTAGLIO = 'Dettaglio Risposte';

function setup() {
  const ss = getSpreadsheet_();
  const risultati = getOrCreateSheet_(ss, SHEET_RISULTATI, risultatiHeaders_());
  const dettaglio = getOrCreateSheet_(ss, SHEET_DETTAGLIO, dettaglioHeaders_());
  formatSheets_(risultati, dettaglio);
  SpreadsheetApp.flush();
  return 'Setup completato. Ora puoi distribuire come App web.';
}

function doGet() {
  return ContentService
    .createTextOutput('Endpoint attivo per Dose Quest Pediatrico. Se leggi questo testo, la Web App funziona.')
    .setMimeType(ContentService.MimeType.TEXT);
}

function doPost(e) {
  const lock = LockService.getScriptLock();
  lock.waitLock(30000);
  try {
    const payload = parsePayload_(e);
    const ss = getSpreadsheet_();
    const sessionId = Utilities.getUuid();

    const risultati = getOrCreateSheet_(ss, SHEET_RISULTATI, risultatiHeaders_());
    const dettaglio = getOrCreateSheet_(ss, SHEET_DETTAGLIO, dettaglioHeaders_());

    risultati.appendRow([
      sessionId,
      payload.submittedAtISO || new Date().toISOString(),
      payload.submittedAtIT || '',
      payload.quizTitle || '',
      payload.studentName || '',
      payload.studentId || '',
      payload.course || '',
      payload.mode || '',
      payload.scorePct || 0,
      payload.correct || 0,
      payload.total || 0,
      payload.durationSeconds || '',
      payload.criticalAreas || '',
      payload.userAgent || ''
    ]);

    const answers = Array.isArray(payload.answers) ? payload.answers : [];
    if (answers.length > 0) {
      const rows = answers.map(a => [
        sessionId,
        a.number || '',
        a.id || '',
        a.area || '',
        a.scenario || '',
        a.question || '',
        a.doseCheckLabel || '',
        a.doseCheckAnswer || '',
        a.doseCheckCorrect === true ? 'Corretta' : (a.doseCheckAnswer ? 'Errore' : ''),
        a.studentAnswer || '',
        a.expectedAnswer || '',
        a.correct === true ? 'Corretta' : 'Errore',
        a.explanation || '',
        a.safety || ''
      ]);
      dettaglio.getRange(dettaglio.getLastRow() + 1, 1, rows.length, rows[0].length).setValues(rows);
    }

    formatSheets_(risultati, dettaglio);
    return json_({ ok: true, sessionId: sessionId });
  } catch (err) {
    return json_({ ok: false, error: String(err && err.message ? err.message : err) });
  } finally {
    lock.releaseLock();
  }
}

function getSpreadsheet_() {
  return SpreadsheetApp.openById(SPREADSHEET_ID);
}

function parsePayload_(e) {
  if (e && e.parameter && e.parameter.payload) {
    return JSON.parse(e.parameter.payload);
  }
  if (e && e.postData && e.postData.contents) {
    try {
      return JSON.parse(e.postData.contents);
    } catch (err) {
      const params = e.postData.contents.split('&').reduce((acc, pair) => {
        const parts = pair.split('=');
        const key = decodeURIComponent(parts[0] || '');
        const value = decodeURIComponent((parts[1] || '').replace(/\+/g, ' '));
        if (key) acc[key] = value;
        return acc;
      }, {});
      if (params.payload) return JSON.parse(params.payload);
    }
  }
  throw new Error('Payload non trovato nella richiesta.');
}

function getOrCreateSheet_(ss, name, headers) {
  let sheet = ss.getSheetByName(name);
  if (!sheet) sheet = ss.insertSheet(name);
  if (sheet.getLastRow() === 0) {
    sheet.getRange(1, 1, 1, headers.length).setValues([headers]);
    sheet.setFrozenRows(1);
  }
  return sheet;
}

function risultatiHeaders_() {
  return [
    'ID sessione', 'Timestamp ISO', 'Data/Ora locale', 'Titolo quiz',
    'Nome studente/gruppo', 'Email o matricola', 'Corso/canale', 'Modalità',
    'Punteggio %', 'Risposte corrette', 'Totale domande', 'Durata secondi',
    'Aree da rinforzare', 'User agent'
  ];
}

function dettaglioHeaders_() {
  return [
    'ID sessione', 'Numero domanda', 'ID domanda', 'Area', 'Scenario',
    'Domanda', 'Check dose richiesto', 'Check dose studente', 'Esito check dose',
    'Risposta finale studente', 'Risposta finale corretta', 'Esito finale',
    'Spiegazione', 'Alert sicurezza'
  ];
}

function formatSheets_(risultati, dettaglio) {
  [risultati, dettaglio].forEach(sheet => {
    const lastCol = sheet.getLastColumn();
    if (lastCol > 0) {
      sheet.getRange(1, 1, 1, lastCol)
        .setFontWeight('bold')
        .setBackground('#ffd3e3')
        .setFontColor('#23304f');
      sheet.setFrozenRows(1);
      sheet.autoResizeColumns(1, lastCol);
    }
  });
}

function json_(obj) {
  return ContentService
    .createTextOutput(JSON.stringify(obj))
    .setMimeType(ContentService.MimeType.JSON);
}
