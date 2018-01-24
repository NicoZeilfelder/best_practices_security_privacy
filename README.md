# Best Practices for Security and Privacy

## Häufige Probleme

### Native Anwendungen:

1. Angriffe auf Endgeräte

   > Das Hauptproblem in der Speicherverwaltung von Android liegt darin, dass andere Anwendungen (teilweise) auf die auf dem Gerät        gespeicherten Daten zugreifen können. Android unterscheidet hierbei zunächst in einen internen und einen externen Speicher. Obwohl die im internen Speicher hinterlegten Daten nur von der jeweiligen Applikation selbst adressiert werden können, kann der externe Speicher global (sowohl lesend als auch schreibend) angesprochen werden. Des Weiteren stellt die Exportfähigkeit externer Medien, wie z.B. von SD-Karten, ein großes Problem dar. Neben dem Datendiebstahl ist es aber auch möglich ausführbare Dateien durch einen Zugriff auf diese direkt im Speicher auszuführen. Content Providers  bieten einen strukturierten Speichermechanismus an, welcher den Zugriff auf die eigene Applikation oder den Zugriff durch andere Anwendungen einschränkt. Durch das Hinzufügen von Berechtigungen, die nicht zwangsläufig erforderlich sind, ist es letztendlich möglich, Angriffe, wie z.B. Code Injection, auszuführen.

2. Angriffe auf das Netzwerk

   > Eine weitere Alternative in Bezug auf native Anwendungen besteht in einem Angriff über das Netzwerk. Dieser ist aus Sicherheitsaspekten sehr riskant, da hierbei potentiell sensible Daten über das Netzwerk übertragen und abgefangen werden können. Diese Art von Angriffen können sowohl über das Internet als auch lokale Netze, wie z.B. öffentliche bzw. unsichere Wi-Fi Hotspots, mit denen sich die Endgeräte automatisch verbinden, erfolgen. Diese können dazu manipuliert werden, um den Netzwerkverkehr mitzulesen oder um an die Daten der Endanwender zu gelangen.

3. Angriffe zwecks mangelnder Eingabevalidierung   

   > Ein weiteres Problem stellt eine mangelnde Eingabevalidierung dar, welche unabhängig von der genutzten Plattform in etwa gleich häufig vorkommt. Die Nutzung von nativem Quellcode kann in fast jeder Anwendung, zum Beispiel durch das Lesen von Dateien oder auch durch die Datenübertragung über das Netzwerk, eine Sicherheitslücke darstellen. Im Umgang mit nativen Applikationen treten einige besondere Angriffe bzw. Sicherheitslücken gesondert auf.

   * Buffer Overflow   

      	> Bei diesem Angriff wird durch einen Fehler im Programm eine zu große Menge an Daten in den Puffer geschrieben, sodass diese die reservierte Speichermenge deutlich überschreitet. Dies führt dazu, dass nachfolgender Speicherstellen überschrieben werden. Im schlimmsten Fall ist es sogar möglich, das Rücksprungadressen überschrieben werden

https://de.wikipedia.org/wiki/Pufferüberlauf

   * Off-By-One Error   
   
      > Ein Off-By-One Error kann bei nativen Anwendungen auftreten und kennzeichnet sich vor allem dadurch, dass die angegebene Speicher- oder Pufferadresse um den Wert eins von der eigentlichen Adresse abweicht. Dadurch wird die Daten der entsprechenden Speicher-/ Pufferstelle überschrieben und es kommt zum Datenverlust und zu Inkonsistenzen. 

https://de.wikipedia.org/wiki/Off-by-one-Error


### Web-Anwendungen: 

1. (Code-/ SQL-) Injection
   > Daten aus Formularen und Parametern werden lokal über den Browser abgesendet und in eine Datenbank eingepflegt. Diese Daten können dann innerhalb der Datenbank in Form von Befehlen ausgeführt werden. Dadurch ist es dem Angreifer möglich die Daten in der Datenbank zu kopieren, zu entfernen oder zu manipulieren. Im Extremfall kann dieser das ganze System übernehmen.   
   
   
2. Fehler in Authentisierung und Session Management
   > Durch Fehler in der Authentisierung oder Fehler im Session Management kann ein Angreifer die Identität eines Benutzers erlangen und dadurch auf dessen Daten zugreifen und bestimmte Transaktionen in dessen Namen tätigen.   


3) Cross Site Scripting (XSS)   
   > Unter XSS wird die Einbindung von Skript-Code (in der Regel JavaScript-Code) über Webseiten im Browser verstanden, welcher dann ausgeführt werden kann. Mit XSS ist es möglich die vorhandene Sitzung zu übernehmen, Seiteninhalte zu verändern und die Aufrufer auf andere Seiten umzuleiten.   

   
4) Unsichere direkte Objektreferenzen   
   > Zugriff auf die Daten anderer Nutzer durch die Anpassung bzw. Veränderung referenzierte Parameter, die nicht ausreichend gesichert wurden. Die URL ```http://example.de/account?id=10``` ermöglicht beispielsweise den Zugriff auf die Daten und Transaktionen des Benutzers mit der Benutzer-ID ```10```. Durch eine Anpassung dieses Parameters mit voraussagbaren Werten, wie z.B. ```id=11``` kann dann auf die Daten und Transaktionen des Benuters ```11``` zugegriffen werden, sofern keine weitere Zugriffskontrolle implementiert wurde.   

   
5) Sicherheitsrelevante Fehlkonfigurationen   
   >Durch die öffentliche Anzeige von Systemfehlermeldungen können die Angreifer an wertvolle Informationen gelangen, welche zur Ausnutzung von Sicherheitslücken bis hin zur Systemübernahme eingesetzt werden können.   


6) Verlust der Vertraulichkeit sensibler Daten   
   > Sensible Daten, wie z.B. Kreditkartendetails, werden bei der Datenübertragung nicht ausreichend verschlüsselt oder in Datenbanken und Log-Files im Klartext gespeichert. Diese können dann von Angreifern eingesehen und missbraucht werden.   

   
7) Fehlerhafte Autorisierung auf Anwendungsebene   
   > Die Realisierung der Zugriffskontrolle erfolgt ausschließlich über das Anzeigen und Ausblenden von Funktionen auf der Benutzeroberfläche. Da der direkte Zugriff auf diese Funktionen ungeprüft bleibt, können Angreifer diese dennoch ausführen und Schaden enrichten.   

   
8) Cross-Site Request Forgery (CSRF)   
   > Unter einem CSRF-Angriff wird der Versand von maniulierten HTTP-Anfragen verstanden. Diese Anfragen werden in der Regel in der Anwendung bzw. im Browser des Opfers ausgeführt, während dieser eingeloggt ist. Durch diese Sicherheitslücke ist der Angreifer in der Lage Transaktionen im Namen des angemeldeten Opfers auszuführen.   

   
9) Nutzung von Komponenten mit bekannten Schwachstelle   
   > Durch Scans oder manuelle Analysen können Angreifer die entsprechende Systemversion von Applikationen identifizieren. Sofern es in der entsprechenden Version etwaige Sicherheitslücken gibt, ist das System durch diese angreifbar.   
   
10) Ungeprüfte Um- und Weiterleitung   
   > Umleitung der Aufrufer auf Phishing-Webseiten oder Seiten mit Schadcode.   

+

## Gegenmaßnahmen

### Native Anwendungen

|Sicherheitslücke|Gegenmaßnahmen|
|---|---|
|Angriffe auf Endgeräte|Speicherung sensibler Daten nur im internen Speicher, Eingabevalidierung, Parametrisierung der Abfragemethoden, Implementierung der Android Application Sandbox, usw.|
Angriffe auf Netzwerke|Kein Vertrauen in heruntergeladene Daten, sicher Protokolle (z.B. HTTPS statt HTTP), Pinning, usw.|

### Web-Anwendungen

|Sicherheitslücke|Gegenmaßnahmen|
|---|---|
|(Code-/ SQL-) Injection|Nutzung von APIs ohne Interpreter, Maskierung spezieller Zeichen, Längenbeschränkung der Eingaben, usw.|
|Fehler in Authentisierung und Session Management |Multi-Faktor Authentisierung, Tests zur Stärke des Passworts, Passwort-Policy (vorgegebene Passwort-Länge, -Eigenschaften und regelmäßige Aktualisierung), usw.|
|Cross Site Scripting (XSS)|Frameworks zur Maskierung von XSS, Reduzierung nicht vertrauenswürdiger HTTP-Anfragen, Einführung einer Content Security Policy, usw.|   
|Unsichere direkte Objektreferenzen|Reduzierung komplexer Dateiformate wie JSON, Implementierung einer Server-Side Input Validation, Authentifizierung je HTTP-Anfrage, Authentisierung mit Cookies usw.|   
|Sicherheitsrelevante Fehlkonfigurationen| Entfernen und Deinstallation nicht benötigter Anwendungen und Frameworks, Einheitliche Konfiguration der Systemlandschaft, usw.|
|Verlust der Vertraulichkeit sensibler Daten|Keine unnötige Speicherung sensibler Daten, Verschlüsselung sensibler Daten, Gewährleistung aktueller und moderner Verschlüssellungsstandards, usw.|
|Fehlerhafte Autorisierung auf Anwendungsebene| Ablehnung der Zugriffsrechte per Default-Einstellung, Implementierung einer Zugriffskontrolle, usw.|
|Cross-Site Request Forgery (CSRF)|Implementierung von Integritätsprüfungen, Einschränkung und Überwachung ein- und ausgehenden Netzwerkverkehrs, usw.|
|Nutzung von Komponenten mit bekannten Schwachstelle|Entfernen ungenutzer Abhängigkeiten/ Features/ Komponenten/ Dateien, Überwachung und Update der Client- und Server-seitigen Komponenten, usw.|
|Ungeprüfte Um- und Weiterleitung|Prüfung auf Weiterleitung, Unterbindung der Weiterleitung, Überwachung der Webseite, usw.|

## Native Anwendungen vs. Web-Applikationen

|Kategorie|Native Anwendungen|Web-Anwendungen|
|---|---|---|


## Literaturverzeichnis

[1] https://developer.android.com/training/articles/security-tips.html#StoringData   
[2] https://developer.android.com/training/articles/security-ssl.html   
[3] https://de.wikipedia.org/wiki/Pufferüberlauf   
[4] https://de.wikipedia.org/wiki/Off-by-one-Error   
[5] https://www.owasp.org/index.php/Main_Page   
[6] https://www.owasp.org/images/7/72/OWASP_Top_10-2017_%28en%29.pdf.pdf   



