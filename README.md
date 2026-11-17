# NEOXIS – Fuga dal Labirinto del Dubbio

Escape room 3D (HTML + three.js) per i laboratori di orientamento nelle scuole medie
dell'**ITCG Luigi Einaudi – Todi**. Età di riferimento: 12-13 anni.

È la versione rivisitata della escape room Genially *"Escape Room Intelligenza Artificiale"*:
stesse stanze, stessa storia dei Neoxis e stesse domande, trasformate in un labirinto 3D da esplorare.

## Come si usa

Apri `index.html` con un browser recente (Chrome, Edge, Firefox, Safari) su PC, LIM o tablet.
Serve una connessione a internet, perché la grafica 3D (three.js) e i font vengono caricati da CDN.

- **Movimento:** frecce o W A S D; su tablet pulsanti a schermo o trascinando il dito.
- **C** cambia inquadratura (ravvicinata / normale / dall'alto).

## La storia

Lo studente, indeciso sulla scuola superiore, viene risucchiato da un'IA nel **Labirinto del Dubbio**.
Sopra i muri fluttuano i suoi dubbi ("Liceo o tecnico?", "E se sbaglio?"...). Per tornare alla realtà
deve recuperare i **4 Neoxis** e riattivare il **Sistema di Controllo** al centro.

| Settore | Colore | Sfida |
|---|---|---|
| Cyber Jungle | verde | 3 domande sulla scuola, 30 secondi per ognuna |
| Cyberzoo | arancione | AFM, SIA, Ragioneria |
| Metabiblioteca | azzurro | prima l'**Oracolo** (storia della tecnologia + IA) dà gli **occhiali scanner**, che rendono visibile il Neoxi; poi 3 domande sul corso SIA |
| Opera Space | magenta | sito, sede, Open Day |

Ogni Neoxi mostra un'operazione: il ragazzo la calcola e deve **ricordare il risultato**.
I 4 numeri formano il codice del Sistema di Controllo (c'è un indizio che costa 50 punti).
Alla fine c'è un **diploma stampabile** con nome, tempo e punteggio.

Altri elementi di gioco: **bit di dati** da raccogliere (+10), **guardiani digitali** che pattugliano
ogni settore (−30 se ti scoprono; la piazza centrale è una zona sicura), minimappa che si svela esplorando,
labirinto diverso a ogni partita e record di tempo salvato sul dispositivo.

## Modificare domande e testi

Tutti i contenuti sono in cima allo script dentro `index.html`, nella sezione **CONTENUTI**:

- `SCUOLA`: nome, sito, indirizzi mostrati nel diploma;
- `SETTORI`: per ogni stanza il titolo, il testo introduttivo, il timer (`0` = nessun timer) e le domande;
- `ORACOLO`: il dialogo con il Professore e le domande dell'Oracolo;
- `DUBBI`: le frasi che fluttuano sopra i muri.

Ogni domanda ha la forma:

```js
{tipo:"singola", q:"Testo della domanda?",
 risposte:[["Risposta giusta",true],["Risposta sbagliata",false]],
 info:"Spiegazione mostrata dopo la risposta giusta"}
```

`tipo` può essere `"singola"`, `"multipla"` (più risposte giuste) o `"vf"` (vero/falso).

Il logo della scuola è incorporato nella pagina; una copia si trova in `assets/logo.jpg`.
