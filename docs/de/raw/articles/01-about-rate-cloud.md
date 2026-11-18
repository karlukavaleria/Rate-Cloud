# Das Angebot von Rate Cloud

[English](../../articles/01-about-rate-cloud.md) · Deutsch · [Français](../../fr/articles/01-about-rate-cloud.md) · [Русский](../../ru/articles/01-about-rate-cloud.md)

Rate Cloud basiert auf einem einfachen Kaufmodell: Sie bezahlen für den Zugang zu einem ausgewählten KI-Modell während eines festgelegten Zeitraums und nutzen dessen API ohne kumulatives Tokenkontingent. Das ist besonders nützlich, wenn eine Anwendung viele Modellaufrufe ausführt und nutzungsabhängige Tokenkosten schwer planbar sind.

Ein autonomer Programmieragent kann ein Repository lesen, Änderungen planen, Dateien bearbeiten, Werkzeuge aufrufen, Fehler prüfen und den Ablauf wiederholen. Jeder Zyklus kann weitere Anfragen und zusätzliche Ein- und Ausgabetokens verursachen. Der Abonnementpreis steigt während der Laufzeit nicht mit der verbrauchten Tokenzahl.

## Unbegrenzte Tokens, begrenzte Verarbeitungskapazität

Unbegrenzte Tokens bedeutet, dass Rate Cloud während eines bezahlten Zeitraums kein tägliches, wöchentliches oder monatliches Gesamtlimit für Ein- und Ausgabetokens festlegt. Eine einzelne Anfrage kann dennoch keinen unbegrenzten Kontext enthalten und nicht unbegrenzt laufen. Kontextkapazität, Fristen, gleichzeitige Verarbeitung, Schutzgrenzen, Hardwarekapazität und Verfügbarkeit bleiben begrenzt.

Das tatsächliche monatliche Volumen hängt vom Modell, der Länge von Eingabe und Antwort, der Geschwindigkeit und der verfügbaren Parallelität ab. Beispiele mit Hunderten Millionen oder Milliarden Tokens erläutern das Preisprinzip, sie versprechen kein monatliches Verarbeitungsvolumen.

## Vier gleichzeitige Slots je kostenpflichtigem Abonnement

Jedes kostenpflichtige Abonnement stellt vier gleichzeitige Anfragen für sein Modell bereit. Ein Slot steht für eine gerade verarbeitete Anfrage. Nach deren Abschluss wird er wieder frei. Es handelt sich nicht um ein Limit von vier Anfragen pro Tag oder Monat.

Das Konto hat zunächst ein Limit von 20 gestarteten Anfragen pro Minute (RPM). Der erste bezahlte Kauf oder die erste bezahlte Verlängerung eines Modell- oder Full-model-Abos zum neuen Preis erhöht das Limit auf 25 RPM, auch bei Zahlung mit Bonusguthaben. Alte Rechnungen, Testzugänge und Geschenke führen nicht zu 25 RPM. Alle Modelle, API-Schlüssel und Verbindungen teilen sich dieses Limit. Sobald das Konto für 25 RPM berechtigt ist, kann ein separates Limit-Upgrade für 30 Tage gekauft werden. Upgrades sind nicht kombinierbar, es gilt ein einziges ausgewähltes Kontolimit. Nach Ablauf gilt wieder das Basislimit. RPM-Upgrades fügen keine parallelen Modell-Slots hinzu. Preis für 30 Tage. 30 RPM / $14,55 · 35 RPM / $32,75 · 40 RPM / $55,49 · 45 RPM / $83,91 · 50 RPM / $119,44. Eine 429-Antwort wegen des Ratenlimits bedeutet, dass das Konto sein Anfragekontingent im gleitenden Zeitfenster erreicht hat. Eine 429-Antwort wegen des Slotlimits bedeutet, dass alle zutreffenden gleichzeitigen Slots belegt sind. Das sind getrennte Limits.

Ein Entwickler kann die Slots für einen Hauptagenten und drei Unteragenten, vier getrennte Arbeitssitzungen oder unabhängige Automatisierungen verwenden. API-Schlüssel desselben Kontos teilen sich den Slot-Pool des betreffenden Modells. Zusätzliche Schlüssel schaffen keine zusätzliche Kapazität.

Abonnements lassen sich kombinieren. Zwei Abonnements desselben Modells ergeben acht Slots für dieses Modell. Abonnements für unterschiedliche Modelle haben getrennte Pools, zum Beispiel vier GLM- und vier DeepSeek-Slots. Die Anfragen müssen an das jeweilige Modell gesendet werden.

## Laufzeiten und Einstieg

Die Website bietet Abonnements für 3, 7 und 30 Tage. Neue Nutzer können die Modelle während der ersten drei Stunden nach Registrierung und erforderlicher E-Mail- und Telegram-Bestätigung mit einem gleichzeitigen Slot testen. Testzugang und kostenpflichtige Abonnements haben unterschiedliche Kontingente.

Beginnen Sie mit einer repräsentativen Aufgabe: einem Repository, einem typischen Dokument oder einem echten Automatisierungsablauf. Prüfen Sie die Antwort, das Verhalten der Werkzeuge und die gesamte Zeit bis zu einem brauchbaren Ergebnis, bevor Sie Modell und Laufzeit auswählen.

## Geeignete Einsatzbereiche

Rate Cloud kann als Modellebene für Programmieragenten, interne Assistenten, Bots, Datenextraktion, Dokumentenabläufe und eigene Produkte dienen. Ein kompatibler Client stellt seine Oberfläche, Werkzeuge, Projektanweisungen und den Verlauf bereit. Welche modellabhängigen Funktionen verfügbar sind, hängt vom Modell und der Integration ab.

Der Dienst verkauft API-Zugang. Eine vertraute Anwendung zu verbinden macht das gewählte GLM-, DeepSeek- oder Qwen-Modell nicht zu einem eigenen Modell des Anwendungsanbieters.

Quellen: [Rate-Cloud-Startseite](https://rate-cloud.com/) und [Funktionsweise](https://rate-cloud.com/how-it-works). Stand: 3. November 2026. [Zur Übersicht](../README.md).

## Full model

Full model umfasst die fünf aktuellen Modelle: GLM 5.3, GLM 5.3 Flash, DeepSeek V4.1 Flash, DeepSeek V4 Pro und Qwen 3.8 Max.

Ein Paket kostet $62.48 für 30 Tage, $31.24 für 7 Tage oder $18.75 für 3 Tage. Ein 10%-Code senkt die Beträge auf $56.24, $28.12 und $16.88, anhand des öffentlichen Wechselkursstands vom 18. November 2026. Prüfen Sie den Bestellbetrag vor der Zahlung.

Jedes Paket fügt jedem Modell einen parallelen Slot hinzu. Paketmengen stapeln sich gleichmäßig über alle Modelle und können nicht umverteilt werden: Zwei Pakete erlauben zwei gleichzeitige Anfragen je Modell. Ein zusätzlicher Kauf fügt Slots für die bezahlte Laufzeit hinzu. Die Verlängerung der gewählten Paketmenge verlängert die Laufzeit ohne Änderung der Slotzahl. Einzelabos bieten unabhängige Kapazität. Für den ersten Kauf gelten die üblichen Regeln für Gutscheine, Empfehlungen und Boni. Eine manuelle Verlängerung ist eine neue Bestellung und kann einen Gutscheincode oder Boni verwenden, wenn das Konto die üblichen Voraussetzungen erfüllt. Die automatische Verlängerung über Whop wird zum vollen vereinbarten Preis berechnet, ohne den Einführungsrabatt erneut anzuwenden.
