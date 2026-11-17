# 🌱 Serra intelligente con Arduino

Serra automatizzata basata su **Arduino Uno R4** che monitora le condizioni ambientali e irriga la pianta in modo autonomo. Progetto scolastico, **in sviluppo**.

## Cosa fa

- Misura **temperatura e umidità dell'aria** (DHT11).
- Misura **l'umidità del terreno** (sensore capacitivo analogico).
- Mostra i valori su un **display LCD 16x2 I2C**.
- Attiva una **pompa 12V** tramite modulo relay quando il terreno è troppo secco.

## Hardware

| Componente | Ruolo |
|---|---|
| Arduino Uno R4 | Microcontrollore |
| DHT11 (modulo a 3 pin) | Temperatura e umidità dell'aria |
| Capacitive Soil Moisture Sensor v1.2 | Umidità del terreno (analogico) |
| LCD 16x2 I2C | Visualizzazione dati |
| Modulo relay 1 canale | Comando della pompa |
| Pompa 12V | Irrigazione |
| Breadboard, cavi, diodo di protezione | Collegamenti |

Schema dei collegamenti: [`guida_cablaggio_serra.md`](guida_cablaggio_serra.md)

## Librerie necessarie

Da installare dal Library Manager dell'Arduino IDE:

- `hd44780` (Bill Perry), per l'LCD I2C
- `DHT sensor library` (Adafruit)
- `Adafruit Unified Sensor`

`Wire` è già inclusa nell'IDE.

## Struttura del progetto

```
serra-intelligente/
├── README.md
├── guida_cablaggio_serra.md
├── codice_comune/      # DHT11 + LCD
├── calibrazione_suolo/ # lettura del sensore di umidità del terreno
└── pompa_suolo/        # logica di irrigazione (da completare)
```

> In aggiornamento

## Stato del progetto

- [x] Lettura DHT11 e visualizzazione su LCD
- [ ] Calibrazione del sensore di suolo (valori secco / bagnato)
- [ ] Logica della pompa in base all'umidità del terreno
- [ ] Test del relay e della pompa
- [ ] Unione di tutte le parti in un unico programma 

## Calibrazione

I valori di soglia dipendono dal singolo sensore e vanno **misurati**: sensore all'aria (secco) e sensore in acqua (bagnato). Nel codice restano segnati come `blank` finché non vengono misurati.

## ⚠️ Sicurezza

- Collegare e scollegare i cavi sempre a circuito **spento**.
- Tenere l'elettronica lontana dall'acqua.
- Non far funzionare la pompa a secco.
- Non far passare la corrente della pompa dalla breadboard.

## Autore

Nicolò

## Licenza

Da definire.
