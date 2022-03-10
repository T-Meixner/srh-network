## Ethernetframe Aufbau

## IEEE 802.3

> IEEE 802.3 beschreibt das grundlegende Ethernet-Frame-Format, das für MAC-Implementierungen erforderlich ist.
>
> - Ethernet-Frame beginnt mit Preamble und SFD, beide arbeiten auf der physikalischen Schicht.
> - Der Frame enthält die Quell- als auch die Ziel-MAC-Adresse und die zu übertragenden Daten.
> - Als letztes Feld steht eine Prüfsumme, die verwendet wird, um den Fehler zu erkennen.

<br>

| PRE    | SDF    | DA     | SA     | Length | Data                | FCS/CRC |
| :----- | :----- | :----- | :----- | :----- | :------------------ | :------ |
| 7 Byte | 1 Byte | 6 Byte | 6 Byte | 2 Byte | 46 Byte - 1500 Byte | 4 Byte  |
| 56 Bit | 8 Bit  | 48 Bit | 48 Bit | 16 Bit | 368 Bit - 12000 Bit | 32 Bit  |

### Preamble (PRE)

Ethernet-Frame beginnt mit einer 7-Byte-Preamble, der Beginn des Frames zeigt und ermöglicht es Sender und Empfänger eine Bit-Synchronisierung herzustellen.

- Zeigt dem Empfänger an, dass ein neuer Frame beginnt, und ermöglicht dem Empfänger, sich mit den Datenstrom zu synchronisieren, bevor die Adressen und die Datenübertragung beginnen.

### Start of frame delimiter (SFD)

Der SDF ist ein 1-Byte-Feld, das immer auf `10101011` gesetzt ist.

- Zeigt an, dass die darauffolgenden Bits die Zieladresse repräsentieren.
- Wird Teilweise als Teil von Preamble (PRE) angesehen.

### Destination MAC-Address (DA)

Ein 6-Byte-Feld, das die MAC-Adresse der Maschine enthält, für die die Daten bestimmt sind.

### Source MAC-Address (SA)

Ein 6-Byte-Feld, das die MAC-Adresse des Quellcomputers enthält.

### Length

Ein 2-Byte-Feld, das die Länge des gesamten Ethernet-Frames angibt.

- Kann einen Wert zwischen `0` und `65534` enthalten, aber die Länge kann aufgrund Beschränkungen von Ethernet nicht größer als `1500` sein.

### Data / Payload

Enthält die die zu übertragenden Daten.

- Die maximal übertragene Daten können bis zu 1500 Bytes betragen.
- Wenn die Datenlänge kleiner als die Mindestlänge von 46 Bytes ist, müssen die restlichen Stellen mit Nullen aufgefüllt werden, um die minimal mögliche Länge zu erreichen.

### Frame Checksum Sequence (FCS) / Cyclic Redundancy Check (CRC)

FCS, bzw. CRC, ist ein 4-Byte-Feld, das einen 32-Bit-Hash-Code von Daten enthält

- Wird über die Felder Zieladresse (DA), Quelladresse (SA), Länge und Daten generiert wird.
- Wenn die vom Ziel berechnete Prüfsumme nicht mit dem gesendeten Prüfsummenwert übereinstimmt, sind die empfangenen Daten beschädigt.

<br>

---

```md
# to-dos

- X IEEE 802.3

  - X 1500Bytes

- CSMA/CD

  - Abgehört Leitungsabfrage CSMA
  - Kollisionsdedektion CD

- X Aufbau

  - X Preamble Zeitliche Synchronisation und Zeitgewinn Empfänger

- 100Base TX und FX

  - beide identisch -> Unterschied Twisted Pair und Glasfaser
```
