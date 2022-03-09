## Netzwertkkomponenten

> ```md
> - ONSI Schichten
> - Bridge Begrenzen Kollisionsdomänen Source Adresse wird gelernt (learning)
>   => Einlagerung in MAC Adressentabelle
>   - Aging
>     => alte MAC Adressen raus wenn Rechner inaktiv, aktive gelangen obere Position in Tabelle (schnellere Abarbeitung)
>     - Store-and-Foreward
>       => Datenpaket wird gespeichert und Destination ermittelt
>   - Cut-Trough
>     => liest nur erste 6 Bytes
>     => kein ganzes Lesen der MAC Adresse
>   - Adaptive-Cut-Trough
>     => Store-and-Foreward
>     => danach Cut-Trough
> ```
