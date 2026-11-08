# Laboratorio binario

Giochi interattivi per imparare a convertire i numeri **da decimale a binario** e **da binario a decimale**. Sono pensati per la classe e seguono passo per passo due schede di esercitazione.

Ogni gioco è una sola pagina HTML. Non serve installare niente: basta aprire il file nel browser, oppure pubblicarlo con GitHub Pages e dare il link agli studenti.

## I giochi

| File | Contenuto | Quando usarlo |
|---|---|---|
| [`decimale-binario.html`](decimale-binario.html) | Solo **decimale → binario** | Prima lezione |
| [`binario-decimale.html`](binario-decimale.html) | Solo **binario → decimale** | Seconda lezione |
| [`index.html`](index.html) | **Tutte e due** le conversioni, con un selettore in alto | Ripasso o verifica |

### Decimale → binario: metodo delle divisioni successive per 2

Lo studente completa la tabella *Dividendo : Divisore = Quoziente | Resto* una riga alla volta.

1. Parte dal numero dato e lo divide per 2.
2. Scrive il quoziente e il resto.
3. Il quoziente diventa da solo il dividendo della riga successiva.
4. Continua finché il quoziente diventa 0.
5. Tocca i resti **dal basso verso l'alto** per comporre il numero binario.

Il gioco contiene gli esercizi della scheda, **52**, **17** e **150**, più una **Sfida** con numeri casuali su tre livelli:

| Livello | Numeri |
|---|---|
| Facile | da 5 a 31 |
| Medio | da 32 a 255 |
| Difficile | da 256 a 1023 |

Alla fine compare un riepilogo, per esempio *52 in binario = 110100*. In questa parte non si usano le potenze di 2, perché gli studenti non le hanno ancora viste.

### Binario → decimale: posizioni e potenze di 2

- **Osserva:** gli esempi **101 = 5** e **1011 = 11**, spiegati un passo alla volta con i pulsanti Avanti e Indietro.
- **Esercizi:** **1001**, **11011** e **100110**. Lo studente compila la tabella in quattro passi:
  1. **Posizioni**, scritte partendo da destra con lo 0. Le caselle si sbloccano una alla volta, da destra verso sinistra.
  2. **Potenze di 2**, per esempio 2³ = 8.
  3. **Cifra × potenza**.
  4. **Somma** dei risultati.
- **Sfida:** numeri binari casuali.

| Livello | Cifre |
|---|---|
| Facile | 3–4 |
| Medio | 5–6 |
| Difficile | 7–8 |

## Come funziona il gioco

- **Aiuti mirati.** Quando una risposta è sbagliata, la casella diventa rossa e compare un suggerimento. Per esempio: *"17 è dispari: togli 1 e poi fai la metà"*, *"2³ vuol dire 2 × 2 × 2"*, *"Si legge dal basso verso l'alto"*.
- **Soluzione.** Dopo due errori sullo stesso passo si può vedere la soluzione. Conta comunque come errore.
- **Punti e stelle.** Ogni riga giusta vale 10 punti e il risultato finale 20. Ogni esercizio dà da 1 a 3 stelle:
  - 3 stelle senza errori;
  - 2 stelle con uno o due errori;
  - 1 stella se l'esercizio è finito comunque.
- **Serie.** Nella Sfida conta quanti esercizi di fila sono stati completati senza errori, e c'è un record.
- **Passi del metodo.** Un pannello laterale evidenzia il passo del metodo a cui è arrivato lo studente.
- **Salvataggio.** Punti, stelle e record restano salvati nel browser di ogni studente con `localStorage`. Non si usano account e nessun dato lascia il dispositivo.
- **Dispositivi e accessibilità.** I giochi funzionano su computer, tablet e telefono, con tema chiaro e scuro automatico. Si possono usare anche solo con la tastiera: **Invio** passa alla casella successiva e controlla la riga.

## Pubblicare con GitHub Pages

1. Carica i file in un repository GitHub.
2. Vai in **Settings → Pages**.
3. In **Build and deployment** scegli *Deploy from a branch*, poi il branch `main` e la cartella `/ (root)`.
4. Dopo qualche minuto i giochi sono online:
   - `https://<utente>.github.io/<repository>/`: tutte e due le conversioni
   - `https://<utente>.github.io/<repository>/decimale-binario.html`
   - `https://<utente>.github.io/<repository>/binario-decimale.html`

Per provarli senza pubblicarli, apri uno dei file `.html` con un doppio clic.

## Struttura

```
.
├── index.html               # entrambe le conversioni
├── decimale-binario.html    # solo decimale → binario
├── binario-decimale.html    # solo binario → decimale
└── README.md
```

Ogni file è autonomo: HTML, CSS e JavaScript sono tutti nello stesso file, senza librerie. Servono solo i font di Google Fonts. Senza connessione il gioco funziona lo stesso, con i font di sistema.

## Personalizzare

Tutto si modifica nello `<script>` in fondo a ogni file.

- **Cambiare gli esercizi:** modifica l'array `levels` dentro `MODES`. Per
