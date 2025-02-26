![[Pasted image 20250226201641.png]]
## Ziele der Kryptographie

- **Vertraulichkeit**:
  Alice möchte eine Nachricht über einen unsicheren Kanal an Bob senden, und dabei sicherstellen dass die Nachricht nur von Bob und nicht von Oscar entziffert werden kann.
- **Integrität**:
  Bob möchte sicherstellen, dass die Nachricht nicht von Oscar manipuliert wurde.
- **Authentizität**:
  Bob möchte sicherstellen, dass die Nachricht tatsächlich von Alice, und nicht von Oscar stammt.
- **Verbindlichkeit**:
  Bob möchte gegenüber Jeffrey beweisen, dass die Nachricht tatsächlich von Alice gesendet wurde.

## [Kerckhoffs-Prinzip](https://de.wikipedia.org/wiki/Kerckhoffs%E2%80%99_Prinzip)

>Die Sicherheit eines kryptographischen Systems darf ausschließlich von der Geheimhaltung des Schlüssels aber nicht von der Geheimhaltung des Verwendeten Algorithmus abhängen.

Die Verschlüsselung muss also auch dann sicher sein, wenn dem Angreifer der Prozess zur Verschlüsselung bekannt ist.

**Beispiele für Systeme bei denen Kerckhoffs-Prinzip nicht beachtet wurde:**
- [Stromchiffren](https://de.wikipedia.org/wiki/A5_(Algorithmus)) A5/1 A5/2 des GMS-Mobilfunksystems
- [DECT-Standard](https://de.wikipedia.org/wiki/Digital_Enhanced_Cordless_Telecommunications)
- [RFID-Technologie](https://de.wikipedia.org/wiki/RFID) Mifare Basic

## Angriffe auf kryptographische Verfahren

Kryptosysteme basieren häufig auf der Annahme, dass eine Entschlüsselung des Geheimtextes zum Klartext mit einem zu hohen Aufwand verbunden ist um praktisch möglich zu sein.

>[!WARNING] Warnung
>Keine perfekte Sicherheit!

### Klassische Kryptoanalyse
Bestimmung von entweder Schlüssel oder Klartext. Wenn Schwachstellen existieren oder die Schlüssellängen zu gering sind ist dies mit vertretbarem Aufwand möglich.
### Implementierungsangriffe
Angriffe auf die **Software oder Hardware** der Implementierung.
- **Software**:
  Gezielte Fehleingaben können unter Umständen Rückschlüsse auf Klartext oder Schlüssel ermöglichen.
- **Hardware**:
  Messung von Strom/Temperatur oder anderer physikalischen Parametern um Kryptosystem zu kompromittieren.
### Social-Engineering-Angriffe
Häufig ist der Mensch das schwächste Glied in der Verschlüsselung. Durch einen Angriff auf Benutzer kann ein Angreifer sensible Daten wie Passwörter erhalten.

**Beispiele für Social-Engineering-Angriffe**:
- [Phishing-Angriffe](https://de.wikipedia.org/wiki/Phishing)
- [Skimming-Angriffe](https://de.wikipedia.org/wiki/Skimming_(Betrug))

## Symmetrische Verschlüsselung

Bei einer symmetrischen Verschlüsselung muss der Schlüssel zuvor über einen sicheren Kanal ausgetauscht werden (z.B. persönlich Übergeben). Anschließend können verschlüsselte Nachrichten über unsicheren Kanal ausgetauscht werden.
![[Pasted image 20250226205938.png]]
> [!INFO] Nomenklatur
> Klartext = x; Geheimtext (Chiffrat) = y; Schlüssel = k; Verschlüsselung = e(); Entschlüsselung = d()

### Substitutionschiffren
- [Monoalphabetische Substitutionschiffre](https://www.cryptool.org/de/cto/monoalpha/)
- [Caesar-Chiffre](https://www.cryptool.org/de/cto/caesar/)
- [Vigenere-Chiffre](https://www.cryptool.org/de/cto/vigenere/)

>[!INFO] One-Time-Pad
>Eine **modifizierte Vigenere-Chiffre** kann perfekt sicher sein, wenn
>- die Schlüssellänge (mindestens) so lang ist wie die Nachricht
>- die Schlüssel gleichverteilt zufällig sind
>- ein Schlüssel nur einmal vewendet wird (auch nicht in Teilen)

