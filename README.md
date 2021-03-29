# BlockchainVotingSystem

Eine der Anforderungen in Bezug auf die Integrität einer Online-Wahl ist, dass zum
Schluss das Wahlergebnis überprüfbar sein muss. Die notwendige Geheimhaltung bei
einer Wahl macht es jedoch schwer, ein Verfahren zu entwickeln, welches einerseits
einfach für Wählerinnen und Wahlbeobachter zu handhaben ist und andererseits
gewährleistet, dass einzelne Stimmen und das Wahlergebnis insgesamt überprüfbar
sind. Diese Anforderung wird in der Fachliteratur als End-To-End Verifiability,
abgekürzt E2E-V bezeichnet.

End-To-End Verifiability wird in der englischen
Fachliteratur auf eine kurze Formel gebracht:
The verification objectives can be summarized with the catchphrase, “Cast as intended;
recorded as cast; and counted as recorded.” 
Das bedeutet, dass überprüfbar sein muss:
1. Wurde der beabsichtigte Kandidat gewählt. Wenn beispielsweise die Kandidaten
auf den Listen vertauscht würden, könnte ein Wähler unbeabsichtigt die falsche
Wahl treffen.
2. Wurde die Stimme so übermittelt und gespeichert, wie gewählt. Durch
Manipulationen bei der Übermittlung oder Speicherung können bei einem Online-
Wahlsystem Stimmen verloren gehen, oder doppelt gespeichert werden.
3. wurde die Stimme auch so gewertet wie gespeichert.

## Authentifizierung und Anonymität

Für eine demokratische Wahl muss auch gewährleistet werden, dass nur berechtigte
Wählerinnen ihre Stimme abgeben können und dass jeder die gleiche Anzahl von
Stimmen hat. Gleichzeitig muss die Anonymität der abgegebenen Stimmen gewahrt
bleiben. Bei einem Peer-To-Peer-Netzwerk auf Basis des Bitcoin-Protokolls ist eine
Authentifizierung nicht vorgesehen, jeder kann Teilnehmer in dem Netzwerk werden
und alle Transaktionen beobachten. Die Eigenschaft des Netzwerks, über eine native Währung (Coins)
zu verfügen, kann für ein Online-Wahlsystem ausgenutzt werden, um den Wählern ihre Stimmen zuzuteilen.
Nur berechtigte Wähler bekommen Coins für die jeweilige Wahl.

## Geheimhaltung und Mechanismus gegen Erpressungen

Ein Online-Wahlsystem muss eine geheime Wahl garantieren. Da eine Online-Wahl
unter „unkontrollierten“ Bedingungen stattfindet (nicht im Wahllokal sondern zuhause
auf unsicheren Endgeräten), muss außerdem sichergestellt werden, dass kein
massenhafter Stimmenkauf, Erpressung etc. technisch ermöglicht wird, ohne dass dies
entdeckt wird. Das bedeutet, dass das System beispielsweise nicht offenbaren darf, wie
ein bestimmter Wähler gewählt hat.

Das Problem der potentiellen Erpressbarkeit erweitert die Anforderung der bloßen
Geheimhaltung: Die Gefahr, dass Stimmen gekauft oder erpresst werden, lässt sich nur
verhindern, wenn eine Wählerin nicht die Möglichkeit hat, zu beweisen, wie sie gewählt
hat. Wäre sie dazu in der Lage, könnte ein Erpresser diesen Beleg fordern und sie wäre
erpressbar. Eine Anforderung, die deswegen an elektronische Wahlsysteme gestellt
wird, wird in der Literatur als „Coercion resistance“ - zu Deutsch etwa
„Widerstandsfähigkeit gegen Erpressung“ bezeichnet. Ein möglicher Erpresser darf
außerdem auch ohne Kooperation der Wählerin keine Möglichkeit haben, eine
Verbindung zwischen der Wählerin und ihrer Wahlentscheidung herstellen können
dürfen. Um die Anforderungen betreffs der Geheimhaltung und Widerstandsfähigkeit zu
erfüllen, ist es notwendig, die Wahlentscheidungen bei der Übertragung in die
Blockchain so zu verschlüsseln, dass ein Erpresser keine Möglichkeit hat, vom Opfer
oder dem Computer des Opfers einen Schlüssel zur Entschlüsselung der Daten zu
bekommen, um Kenntnis über die tatsächliche Wahlentscheidung der Wählerin zu
erlangen – sei es mit oder ohne Kooperation der Wählerin.

## Blockchain-basierte Netzwerke zur Durchführung von Online-Wahlen

Die Blockchain-Technologie, die mit der Erfindung der digitalen Kryptowährung
Bitcoin, bekannt wurde, könnte das zentrale Problem der Transparenz und des
Vertrauens bei Online-Wahlen lösen und andere Sicherheitsprobleme entschärfen. Im
Gegensatz zu den bisher verwendeten Server-Client-Architekturen besteht der Kern
der Blockchain-Technologie aus einer mittels Peer-To-Peer-Protokoll verteilten
Datenbank, deren Integrität durch einen kryptografischen Hash-Algorithmus
sichergestellt wird. Dadurch sind alle Vorgänge in dieser Datenbank für die
Teilnehmer zugänglich und transparent. Bezogen auf ein Wahlsystem hieße das, dass
alle Stimmzuweisungen und Stimmabgaben sicher aufgezeichnet würden und jeder
die Gültigkeit dieser Informationen überprüfen kann. Jeder Wähler kann zum Schluss überprüfen: Wurde meine
meine Stimme wie beabsichtigt zugeordnet? Wurde meine Stimme gezählt wie
zugeordnet und werden alle Stimmen gezählt?

Bei konventionellen Kryptowährungen, wie zum Beispiel dem Bitcoin-Netzwerk, ist keine Geheimhaltung der
Informationen und der Metadaten vorgesehen. Jede Transaktion läßt sich transparent zum Absender und Empfänger verfolgen. Dadurch würde die Anforderung an ein elektronisches Wahlsystem, eine geheime Wahl zu ermöglichen und resistent gegen Erpressungsversuche zu sein, nicht erfüllt werden.
Es gibt jedoch Weiterentwicklungen von Kryptowährungen, die das Problem adressieren: Techniken wie zum Beispiel "Ring-Signaturen" ermöglichen den Schutz der Privatssphäre, ohne die Sicherheit und Konsistenz der Blockchain-Datenbank zu gefährden.

### Funktionsweise von Blockchain basierten Wahlsystemen

Je nach Szenario, zum Beispiel staatlich organisierte allgemeine Wahlen, oder interne Abstimmungen in Unternehmen, benötigt man eine Anzahl sogenannter "Mining-Nodes" für das Errechnen der Transaktionen, eine App, die den Teilnehmer*innen, die Registrierung, Durchführung und Überprüfung der Wahlergebnisse ermöglicht und dazu die Anwendungen für die Korrekte Auswertung, Publizierung und Darstellung der Wahlergebnisse.

#### Mining Nodes

Für alle Szenarien gilt, dass Mining, der veranstaltenden Organisation vorbehalten bleibt. Für Wahlen braucht man nur so viele Einheiten einer nativen Währung, wie maximal Stimmen abgegeben werden können. Da bei diesem Wahlsystem die geschürfte native Währung zur Stimmenabgabe und -Auszählung dienen soll, dürfen keine Einheiten dieser nativen Währung außerhalb der Organisation geschürft werden. Es sollten jedoch mindestens so viele Mining-Nodes existieren, dass alle Transaktionen ohne Wartezeit angenommen werden können.

#### Blockchain-Architektur

Die Geschwindigkeit der Blockgenerierung und die Blockgröße haben einen entscheidenden Anteil daran, wie wiele Transaktionen in einer bestimmten Zeit abgearbeitet werden können. Fast alle bisherigen Kryptowährungen hatten bei zunehmender Beliebtheit Probleme mit der Kapazität. Ein Wahlsystem muss die auftretenden Spitzenbelastungen sicher bewältigen können ohne dass Benutzer*innen entäuscht werden oder das System gar verlassen. Die Blockchain sichert die Anonymität ihrer Benutzer durch Ring-Identitäten und der Verschleierung des Inhalts der jeweiligen Transaktionen. Mechanismen gegen "Double Spending" werden durch erweiterte Konsistensprüfungen der Nodes in der Blockchain realisiert.

#### Wallets als Wahlapp

