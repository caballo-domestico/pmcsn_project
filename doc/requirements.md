# Requisiti

Questo documento presenta i requisiti prelevati da  [qui](https://docs.google.com/document/d/1p5BETXq3lr1QX4pSG3HxUtD5wzGthiCzQcyGOeRiaVQ/edit?usp=sharing) che passano la revisione dei membri del progetto, così da poter avere tutte le versioni dei requisiti sulla repository.

## Progetto:

Altre idee:
- Fotocopisterie a distanza: mail, chiavette
- Login per bonus di stato
- Telefonate/di persona CUP
- Shortage processori (?)
- Dati su trasporto pubblico

- Corridoi umanitari Uraina/altre guerre
  - Chi sono i serventi? Quali sono i punti di snodo? (accessibili: si/no)
  - serventi: qualche città ucraina 
  - code: punti di accesso ai confini
  - Approvvigionamento cibo e medicine
  - Ritardo rifornimenti (delivery lag)
  - Rifornimenti rispresi (traffico rifiutato)
  - Ricerca dati da: emercency, unicef, amnesty

### Note:
Eventuale aggiunta flusso di persone in uscita
Eventuali punti intermedi per controlli (checkpoint) / ritardi causa bombardamenti sul percorso

### Descrizione:
Si vuole analizzare un sistema di smistamento aiuti umanitari da parte di Associazione Umanitaria in favore di città occupate di stato in guerra. Gli aiuti partono da punti di accesso sui confini dello stato, e per arrivare alle città devono seguire degli itinerari mediante vettori di trasporto.

### Aiuti: 
- Dimensione aiuti variabile
- Aiuti possono essere medicinali, cibo, carburanti, … (classi di aiuti)

### Vettori:
- Ogni vettore ha una sua capacità
- Un vettore può essere gomma, velivoli, navi, …
- Ogni vettore specifica su quali classi di itinerario può viaggiare

### Itinerario:
- Itinerari divisi in classi (strada, ferrovia, tratta aerea, navale, …)
- Ogni itinerario ha una capienza massima di vettori che lo possono percorrere contemporaneamente
- Un itinerario può essere in stato agibile, occupato, distrutto
  - Agibile: può essere percorso. Può diventare occupato o distrutto
  - Occupato: non può essere percorso, può diventare agibile o distrutto
  - Distrutto: non può essere più percorso.

### Città:
- Ogni città ha una domanda per ogni classe di aiuti
- Ogni città ha un livello di necessità per ogni classe di aiuti

### Punti di accesso:
- Ogni punto di accesso può avere un massimo numero di scorte di classe di aiuto.
- Ogni punto di accesso ha a disposizione delle classi di vettori
- Ogni punto di accesso è collegato a un numero di città mediante degli itinerari

CRITICITÀ da rendere obiettivi

DATI 

