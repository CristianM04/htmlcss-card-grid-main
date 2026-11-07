# htmlcss-card-grid

Esercizio da fare da soli dopo la lezione di sabato 7/11 su CSS Grid. È la pagina di Pinco Pallo del live coding: le stesse colonne di giovedì, ma questa volta con Grid.

## Cosa devi fare

Parti dalla pagina di questa repo: un header, sei card e un banner. Il menu è già fatto. Le card invece stanno una sotto l'altra, attaccate, e il banner è in fondo. Con Grid e le media query fai le colonne come negli screenshot.

**L'HTML non si tocca**: scrivi solo in `css/style.css`, in fondo al file. Si lavora mobile first. Niente Flexbox per le colonne: le fa Grid.

## Cosa trovi qui

```
├── index.html               ← la pagina, da non modificare
├── css/style.css            ← qui scrivi Grid e le media query
├── img/                     ← le immagini delle card
├── screenshot-mobile.jpg    ← la pagina finita a 400px
├── screenshot-tablet.jpg    ← la pagina finita a 800px
└── screenshot-desktop.jpg   ← la pagina finita a 1300px
```

## Come procedere

1. Fai il **fork** di questa repo: bottone **Fork** in alto a destra, lascia il nome `htmlcss-card-grid`. Il fork è la tua consegna: così il docente la vede.
2. Clona il **tuo** fork sul computer (`git clone` con l'indirizzo del tuo fork, non di questa repo).
3. Apri la cartella e lavora con l'inspector aperto. La barra dei dispositivi (`Ctrl+Shift+M` su Windows, `Cmd+Shift+M` su Mac) ti fa scrivere la larghezza esatta.
4. Fai commit e push sul tuo fork.

## I passi

### 1. La griglia

- **Obiettivo**: la `.row` diventa una griglia. A ogni larghezza c'è ancora una card per riga, ma tra una card e l'altra ci sono 24px.
- **Come verifichi**: nell'inspector, accanto alla `.row` compare il badge `grid`. Cliccalo: vedi le linee della griglia sopra la pagina.

<details>
<summary>Suggerimento</summary>

Ti servono due proprietà sul contenitore, nessuna sulle card. Ripassa la dispensa CSS Grid, parte "Definire la griglia".

</details>

### 2. Le colonne

- **Obiettivo**: una colonna sotto i 676px, due da 676px, tre da 876px, quattro da 1200px. Sono le soglie di giovedì: cambia solo il modo di fare le colonne.
- **Come verifichi**: prova a 675, 676, 875, 876, 1199 e 1200px. Le colonne cambiano esattamente alle soglie, tutte larghe uguali e senza barra orizzontale. A 1300px le ultime due card restano larghe come le altre, come nello screenshot.

<details>
<summary>Suggerimento</summary>

Una media query per ogni soglia, dalla più piccola alla più grande. Dentro, una sola proprietà sulla `.row`. Niente `calc()`: il gap lo toglie già Grid. Pensa a `repeat()` e all'unità `fr`.

</details>

### 3. Il banner

- **Obiettivo**: il banner occupa sempre tutta la riga, con qualsiasi numero di colonne. Fino a 875px sta sopra tutte le card, da 876px sotto tutte le card.
- **Come verifichi**: a 875px il banner è la prima cosa sotto l'header, a 876px l'ultima della pagina. A 1300px è largo quanto le quattro colonne insieme.

<details>
<summary>Suggerimento</summary>

Per la larghezza: da quale linea a quale linea della griglia deve andare? C'è un numero che indica sempre l'ultima linea, quante che siano le colonne. Per spostarlo: la proprietà che usavi in Flexbox funziona anche in Grid.

</details>

Per ripassare: [dispensa CSS Grid](https://kb-aiwd.andreadev237.workers.dev/lezioni/css-grid) e [dispensa Media query](https://kb-aiwd.andreadev237.workers.dev/lezioni/css-media-query).

Se usi l'AI, il file `AGENTS.md` la fa lavorare da tutor: ti fa domande e ti indica dove guardare, senza darti la soluzione.

## Bonus (facoltativo)

Commenta le tre media query delle colonne e prova `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));` sulla `.row`. Allarga e stringi la finestra: quante colonne vedi a 600px e a 1300px, e perché? Cosa cambia rispetto alle soglie che hai scelto tu?

## Consegna

Nessuna scadenza. Fai push sul tuo fork, poi incolla il link nel canale del corso.
