# Best Practices for Security and Privacy

## Kategorisierung 

## Häufige Probleme

### Native Anwendungen:

### Web-Anwendungen: 

1) (Code-/ SQL-) Injection   
> Daten aus Formularen und Parametern werden lokal über den Browser abgesendet und in eine Datenbank eingepflegt. Diese Daten können dann innerhalb der Datenbank in Form von Befehlen ausgeführt werden. Dadurch ist es dem Angreifer möglich die Daten in der Datenbank zu kopieren, zu entfernen oder zu manipulieren. Im Extremfall kann dieser gegebenefalls das ganze System übernehmen.

   
2) Fehler in Authentisierung und Session Management   
> Durch Fehler in der Authentisierung oder Fehler im Session Management kann ein Angreifer die Identität eines Benutzers erlangen und dadurch auf dessen Daten zugreifen und bestimmte Transaktionen in dessen Namen tätigen.

   
3) Cross Site Scripting (XSS)   
> Unter XSS wird die Einbindung von Skript-Code (in der Regel JavaScript-Code) über Webseiten im Browser verstanden, welcher dann ausgeführt werden kann. Mit XSS ist es möglich die vorhandene Sitzung zu übernehmen, Seiteninhalte zu verändern und die Aufrufer auf andere Seiten umzuleiten.

   
4) Unsichere direkte Objektreferenzen   
> Zugriff auf die Daten anderer Nutzer durch die Anpassung bzw. Veränderung referenzierte Parameter, die nicht ausreichend gesichert wurden. Die URL ```http://example.de/account?id=10``` ermöglicht beispielsweise den Zugriff auf die Daten und Transaktionen des Benutzers mit der Benutzer-ID ```10```. Durch eine Anpassung dieses Parameters mit voraussagbaren Werten, wie z.B. ```id=11``` kann dann auf die Daten und Transaktionen des Benuters ```11``` zugegriffen werden, sofern keine weitere Zugriffskontrolle implementiert wurde.

   
5) Sicherheitsrelevante Fehlkonfigurationen   
>Durch die öffentliche Anzeiche von Systemfehlermeldungen können die Angreifer an wertvolle Informationen gelangen, welche zur Ausnutzung von Sicherheitslücken bis hin zu Systemübernahme eingesetzt werden können.


6) Verlust der Vertraulichkeit sensibler Daten   
> Sensible Daten, wie z.B. Kreditkartendetails, werden bei der Datenübertragung nicht ausreichend verschlüsselt oder in Datenbanken und Log-Files im Klartext gespeichert. Diese können dann von Angreifern eingesehen und missbraucht werden.

   
7) Fehlerhafte Autorisierung auf Anwendungsebene   
> Die Realisierung der Zugriffskontrolle erfolgt ausschließlich über das Anzeigen und Ausblenden von Funktionen innerhalb der Benutzeroberfläche. Da der direkte Zugriff auf diese Funktionen ungeprüft bleibt, können Angreifer diese dennoch ausführen und Schaden enrichten.

   
8) Cross-Site Request Forgery (CSRF)   
> Unter einem CSRF-Angriff wird der Versand von maniulierten HTTP-Anfragen verstanden. Diese Anfragen werden in der Regel in der Anwendung bzw. im Browser des Opfers ausgeführt, währenddessen dieser eingeloggt ist. Durch diese Sicherheitslücke ist der Angreifer in der Lage Transaktionen im Namen des angemeldeten Opfers auszuführen.

   
9) Nutzung von Komponenten mit bekannten Schwachstelle   
> Durch Scans oder manuelle Analysen können Angreifer die entsprechende Systemversion von Applikationen identifizieren. Sofern es in der entsprechenden Version etwaige Sicherheitslücken gibt, ist das System durch diese angreifbar.

   
10) Ungeprüfte Um- und Weiterleitung   
> Umleitung der Aufrufer auf Phishing-Webseiten oder Seiten mit Schad-Code.

   
Quellen: [1] [2]

## Gegenmaßnahmen

### Native Anwendungen

### Web-Anwendungen

|Sicherheitslücke|Gegenmaßnahmen|
|---|---|
|(Code-/ SQL-) Injection|Nutzung von APIs ohne Interpreter, Maskierung spezieller Zeichen, Längenbeschränkung der Eingaben, usw.|
|Fehler in Authentisierung und Session Management |Multi-Faktor Authentisierung, Tests zur Stärke des Passworts, Passwort-Policy (vorgegebene Passwort-Länge, Eigenschaften und regelmäßige Aktualisierung), usw.|
|Cross Site Scripting (XSS)||   
|Unsichere direkte Objektreferenzen||   
|Sicherheitsrelevante Fehlkonfigurationen||
|Verlust der Vertraulichkeit sensibler Daten||
|Fehlerhafte Autorisierung auf Anwendungsebene||
|Cross-Site Request Forgery (CSRF)||
|Nutzung von Komponenten mit bekannten Schwachstelle||
|Ungeprüfte Um- und Weiterleitung||

## Native Anwendungen vs. Web-Applikationen

## Literaturverzeichnis

[1] https://www.owasp.org/index.php/Main_Page   
[2] https://www.owasp.org/images/7/72/OWASP_Top_10-2017_%28en%29.pdf.pdf   


