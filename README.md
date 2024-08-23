# Riconoscitore Vocale di Emozioni: Rilevamento di Rabbia/Stress

## Introduzione

Questo progetto documenta l'implementazione di un riconoscitore vocale di emozioni, focalizzato sul rilevamento della rabbia e dello stress tramite un approccio di machine learning. Il riconoscimento delle emozioni nella voce rappresenta una componente critica nell'interazione uomo-macchina, con applicazioni che spaziano dagli assistenti virtuali al monitoraggio dello stato mentale di un individuo.

## Obiettivi

Il progetto mira a:
1. Unificare e preprocessare dataset audio per la rilevazione di emozioni.
2. Estrarre caratteristiche vocali utili per la classificazione delle emozioni, concentrandosi su parametri come intensità e frequenza.
3. Implementare un modello predittivo basato su regressione logistica per identificare la presenza di rabbia/stress nell'interlocutore.

## Datasets Utilizzati

Sono stati uniti tre dataset principali:
- **RAVDESS**: 1440 tracce audio di attori che esprimono diverse emozioni.
- **CREMA-D**: 7442 tracce audio di attori che recitano frasi con differenti emozioni e intensità.
- **SAVEE**: 480 tracce audio di attori maschili con diverse emozioni.

Questi dataset sono stati preprocessati e combinati per creare un dataset unico di 9362 campioni.

## Estrarre Caratteristiche Audio

Le caratteristiche vocali principali estratte includono:
- **Zero Crossing Rate**: Tasso di attraversamento dello zero del segnale audio.
- **MFCC (Mel Frequency Cepstral Coefficients)**: Coefficienti che rappresentano le caratteristiche spettrali del segnale audio.
- **Mel Spectrogram Frequency**: Spettrogramma basato sulla scala Mel, che riflette la percezione umana delle frequenze.
- **Chroma Vector e Chroma Deviation**: Rappresentazione delle proprietà armoniche e melodiche del segnale.

Le caratteristiche estratte sono state inserite in un modello di machine learning per la classificazione.

## Modello Predittivo

Per la classificazione binaria dell'emozione (rabbia/stress vs altre emozioni) è stato scelto un modello di regressione logistica, ideale per problemi di questo tipo. L'accuratezza del modello è stata valutata tramite la metrica dell'accuracy e la matrice di confusione.

## Data Augmentation

Per bilanciare il dataset, è stata eseguita un'operazione di data augmentation, introducendo varianti dei campioni di audio con rabbia mediante l'aggiunta di rumore e modifiche al pitch della voce. Questo ha permesso di aumentare il numero di istanze della classe "angry" e di rendere il modello più robusto.

## Esecuzione del Progetto

### Prerequisiti

Per eseguire questo progetto, assicurarsi di avere installato i seguenti pacchetti Python:

```bash
pip install pandas numpy librosa seaborn matplotlib scikit-learn
```

### Avvio del Progetto

1. Clona il repository:

```bash
git clone https://github.com/tuo-username/emotion-recognition.git
```

2. Carica i dataset (RAVDESS, CREMA-D, SAVEE) nelle rispettive directory.
3. Esegui il notebook Python `emotion_recognition.ipynb` per eseguire tutte le fasi del progetto, dal caricamento dei dati all'addestramento del modello.

### Visualizzazione dei Risultati

Il progetto include visualizzazioni come waveplots e spettrogrammi che mostrano le variazioni di ampiezza e frequenza nei segnali audio. Inoltre, i risultati della classificazione sono presentati sotto forma di report di precisione e matrice di confusione.

## Conclusioni

Questo progetto rappresenta un primo passo verso l'implementazione di sistemi di riconoscimento delle emozioni vocali, con un focus specifico sul rilevamento di rabbia/stress. L'integrazione di tecniche di machine learning con l'elaborazione del segnale audio permette di esplorare nuove frontiere nell'interazione uomo-macchina.
