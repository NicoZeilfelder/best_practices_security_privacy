# Best Practices for Security and Privacy

Android stellt etwaige Sicherheits-Features zur Verfügung, welche zu einer signifikanten Reduzierung der Häufigkeit und Auswirkungen von Sicherheitslücken beitragen. Mögliche Kernfeatures zur Schließung der Sicherheitslücken sind beispielsweise

* gaga

## Kategorisierung 




## Häufige Probleme

### Native Anwendungen:



### Web-Anwendungen: 

1) (Code-/ SQL-) Injection   
Daten aus Formularen und Parametern werden lokal über den Browser abgesendet und in eine Datenbank eingepflegt. Diese Daten können dann innerhalb der Datenbank in Form von Befehlen ausgeführt werden. Dadurch ist es dem Angreifer möglich die Daten in der Datenbank zu kopieren, entfernen oder zu manipulieren. Im Extremfall kann dieser gegebenefalls das ganze System übernehmen.

2) Fehler in Authentisierung und Session Management   
Durch Fehler in der Authentisierung oder Fehler im Session Management kann ein Angreifer die Identitä eines Benutzers erlangen und dadurch auf dessen Daten zugreifen und bestimmte Transaktionen in dessen Namen tätigen.

3) Cross Site Scripting (XSS)   
Unter XSS wird die Einbindung von Skript-Code (in der Regel JavaScript) über Webseiten im Browser verstanden, welcher dann ausgeführt werden kann. Mit XSS ist es möglich die vorhandene Sitzung zu übernehmen, Seiteninhalte zu verändern und die Aufrufer der Webseite auf andere Seiten umzuleiten.

4) Unsichere direkte Objektreferenzen   
Zugriff auf die Daten anderer Nutzer durch die Anpassung bzw. Veränderung referenzierte Parameter die nicht ausreichen gesichert wurden. Die URL ```http://example.de/account?id=10``` ermöglicht beispielsweise den Zugriff auf die Daten und Transaktionen des Benutzers mit der Benutzer-ID 10. Durch eine Anpassung dieses Parameters mit voraussichtlichen Werten, wie z.B. ```id=11``` kann dann auf die Daten und Transaktionen (sofern keine weitere Zugriffsrolle implementiert wurde) zugegriffen werden.

5) Sicherheitsrelevante Fehlkonfigurationen

6) Verlust der Vertraulichkeit sensibler Daten

7) Fehlerhafte Autorisierung auf Anwendungsebene

8) Cross-Site Request Forgery (CSRF)

9) Nutzung von Komponenten mit bekannten Schwachstelle

10) Ungeprüfte Um- und Weiterleitung



## Gegenmaßnahmen

## Native Anwendungen vs. Web-Applikationen

|Kategorie|Native Applikationen| Web-Applikationen|
|-------------|------------------------------|-----------------------------|
| a | b | c |


Literaturverzeichnis:

[1] https://www.owasp.org/index.php/Main_Page

[2] https://www.owasp.org/images/7/72/OWASP_Top_10-2017_%28en%29.pdf.pdf

[3] http://blog.brandung.de/die-10-haeufigsten-sicherheitsrisiken
