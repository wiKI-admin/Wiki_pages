# **CAN-Bus**

Besteht aus zwei Leiter die zusammen eine differentielle Leitung bilden
dadurch ist der CAN-Bus gegen Störungen sehr robust.

Die differentielle Leitung funktioniert folgenderweise, auf einen Leiter
wird die positive Spannung gelegt, auf den anderen die negative. Die
Differenz zwischen den beiden ist das was dann geprüft wird den es muss
konstant bleiben.

## **Bitrate und Leitungslänge**

Das CAN Netzwerk kann bis zu 1Mbit/s übertragen. Alle Knoten müssen die
Nachricht gleichzeitig bearbeiten können, das heißt entscheiden ob sie
für den jeweiligen Knoten relevant ist oder nicht.

Die Bitrate hängt mit der Leitungslänge zusammen das heißt je länger die
Leitung langsamer ist die Bitrate.

Dazu gibt es eine Tabelle zu den zu erwartenden Bitraten in Abhängigkeit
von der Länge.

## **Busterminierung**

Der Bus wird mit einem 120 Ohm Widerstand terminiert, dies ist nötig
damit keine Reflexionen und damit die Leiter nicht in der Luft hängen.

Es wird empfohlen beide Enden mit jeweils einen 120 Ohm Widerstand
belegen.

## **Prinzip des Datenaustausches im CAN Netzwerk**

Bei der Datenübertragung werden die Nachrichten und nicht die Knoten
adressiert das heißt, die Nachricht geht an alle Knoten, die Nachricht
ist aber so gekennzeichnet das sie nur die nötigen Anwendungen die
Nachricht annehmen, neben diese Identifizierungsverfahren wird eine
weitere Kennzeichnung gegeben sodass die Priorität der Nachricht auch
berücksichtigt wird.

Durch diese Art der Identifizierung wird eine sehr hohe Flexibilität
erreicht, also es können weitere Knoten an den Bus hinzugefügt werden
ohne an das gesamte System etwas ändern zu müssen.

## **Kollisionsprüfung**

Jeder Teilnehmer kann Daten durch den Bus senden, dadurch können
Kollisionen entstehen. Die werden per Hardware aufgelöst und durch
Wiederholung behoben. Eine Kollision wird erkannt indem der Sender den
gesendeten Identifier selbst zurückliest und vergleicht.

## **Schichten der CAN- Software und Hardware**

Die Schichten folgen einen Teil des OSI Modell also:

  - Physical Layer

  - Transport Layer

  - Object Layer

  - Application Layer

**Physical Layer** ist die wo die Kabel, Spannungen usw. enthalten sind

**Transport Layer** ist die Übertragungsschicht hier ist die Codierung,
das Busprotokoll usw.

**Objektschicht** beinhaltet die Verwaltung von Nachrichten, welche
gesendet werden sollen, welche Priorität, usw.

**Anwendungsschicht** ist für die Verkapselung der Daten als Datenpakete
und deren Kennzeichnung, zuständig

## **Aufbau einer CAN Nachricht**

Die Verpackung einer Nachricht im CAN System wird als Frame bezeichnet,
sie besteht aus folgende Kennfeldern:

  - Start-Condition

  - Message Identifier

  - Steuerbits

  - Daten (0-8 Bytes)

  - Prüfbits

  - Acknowledge-Bit

  - Stop-Condition

Man unterscheidet Frames in Abhängigkeit nach der Länge des Identifiers:

  - Standard Frame (11 Bit Identifier)

  - Extended Frame (29 Bit Identifier)

Nach der Art des Frames unterscheidet man den:

  - Data Frame (Daten werden ohne spezielle Aufforderung gesendet)

  - Remote Data Frame (Daten werden angefordert)

Fehlererkennung im CAN Netzwerk

1.  **Cyclic Redundancy Check**

Sichert die Info des Frames, indem redundante Prüfbits hinzugefügt
werden.

2.  **Frame-check**

Überprüft die Struktur des Frames

3.  **ACK-Fehler**

Im CAN-Protokoll sind zwei Mechanismen zur Fehlererkennung auf Bitebene
implementiert.

1.  **Monitoring**

Jeder Knoten der sendet, beobachtet gleichzeitig den Buspegel. Dabei
werden Differenzen zwischen gesendeten und empfangenen Bit erkannt. Und
somit werden alle globale so wie der lokaler Bitfehler erkannt.

2.  **Bit-Stuffing**

Auf der Bitebene wird die Codierung der Einzelbits überprüft. Das
CAN-Protokoll nutzt die NRZ-Codierung (Non-Return-to Zero).
