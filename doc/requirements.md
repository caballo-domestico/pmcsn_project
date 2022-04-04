# Requisiti

Questo documento presenta i requisiti prelevati da  [qui](https://docs.google.com/document/d/1p5BETXq3lr1QX4pSG3HxUtD5wzGthiCzQcyGOeRiaVQ/edit?usp=sharing) che passano la revisione dei membri del progetto, così da poter avere tutte le versioni dei requisiti sulla repository.

## Progetto:

### Descrizione:
Si vuole analizzare un sistema di smistamento aiuti umanitari da parte di Associazione Umanitaria in favore di città occupate di stato in guerra. Gli aiuti partono da punti di accesso sui confini dello stato, e per arrivare alle città devono seguire degli itinerari mediante vettori di trasporto.

### Aiuti: 
Dimensione aiuti variabile

Aiuti possono essere medicinali, cibo, carburanti, … (classi di aiuti)

### Vettori:
I vettori sono modellati come jobs la cui size corrisponde alla loro capacità

Un vettore può essere gomma, velivoli, navi, …

Ogni vettore specifica su quali classi di itinerario può viaggiare

### Collegamento:
Un collegamento è un tratto che collega due ciità/snodi tra loro

Collegamenti divisi in classi (strada, ferrovia, tratta aerea, navale, …)

Ogni collegamento ha una capienza massima di vettori che lo possono percorrere contemporaneamente

Un collegamento può essere in stato agibile, occupato, distrutto
  - Agibile: può essere percorso. Può diventare occupato o distrutto
  - Occupato: non può essere percorso, può diventare agibile o distrutto
  - Distrutto: non può essere più percorso.

Ogni collegamento è modellato da una coda per ogni verso percorribile i cui occupanti sono i vettori che lo attraversano.

Se un collegamento perde lo stato di Agibile, i vettori che lo stanno attraversando in quel momento si spostano su un altro collegamento.

Ogni collegamento può essere percorso in un verso e nell’altro

### Snodo:
Uno snodo è un punto in cui convergono più collegamenti. Non è una città bisognosa di aiuti.

### Itinerario
Un itinerario è una serie di collegamenti che parte da un Punto di accesso e finisce in una città.

Gli itinerari sono noti a priori al sistema.

### Città:
Ogni città ha una domanda per ogni classe di aiuti

Ogni città ha un livello di priorità per ogni classe di aiuti

Ogni città ha:
  - un numero di cittadini (cfr. Wikipedia)
  - numero di scorte per ogni bene (cercare su internet)
  - una soglia critica delle scorte per ogni bene (una certa percentuale rispetto alla capienza massima, fisso, non da cercare)

Ogni città consuma una certa quantità delle sue scorte per unità di tempo. Tale quantità è proporzionale al numero di cittadini.

Se le scorte di un bene scendono al di sotto della loro soglia critica, un certo numero di cittadini di quella città muore.

### città e snodi:
Ogni città/snodo è modellata come tanti serventi quanti sono i collegamenti entranti in esso. 

Il tempo di servitura di ogni servente è una funzione mu(lunghezzaCollegamentoEntrante, grandezzaCittà, tipoDiCollegamento). Il parametro grandezzaCittà è diverso da zero se e solo se il vettore servito deve consegnare il bene che trasporta in quella città (se è uno snodo tale parametro è sempre zero).

### Punti di accesso:
Ogni punto di accesso può avere un massimo numero di scorte di classe di aiuto.

Ogni punto di accesso ha a disposizione delle classi di vettori

Ogni punto di accesso è collegato a un numero di città mediante degli itinerari

I Punti di accesso definiscono i tassi lambda di arrivi, ovvero i tassi di partenze dei vettori in entrata nel paese.

## Obiettivi:
Minimizzare il numero di morti nelle città a causa dell’esaurimento delle scorte.
