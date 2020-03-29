# cph-ha104-cphbusiness.dk
Security week 9

Vi har været næsten det hele øvelsen igennem. Vi mangler at lave følgende: 
* Create a new folder META_INF in \src\main\resources
* In this folder, create a file persistence.xml ...



SVAR PÅ SPØRGSMÅL:

Week-09 Crypto - 1
Explain conceptually all the following terms, and how/why they are needed for SSH and TLS/SSL 
•	Symmetric Encryption
-	“Symmetrical encryption” er en type af kryptering hvor en “key” kan blive brugt til at krypterer beskeder til den modsatte part, og til at dekrypterer beskeden modtaget fra den anden deltager. Det betyder at enhver som har nøglen kan krypterer og dekrypterer beskeder to enhver anden som har “the key”.

-	Denne type krypterings skema bliver ofte kaldt “shared secret” kryptering  eller “secret key” kryptering. Der er typisk kun en enkelt nøgle, som er brugt til alle operationer.

-	Symetriske nøgler er brugt af SSH for at krypterer hele forbindelsen. Modsat hvad nogle brugere antager: offentlige/private asymmetriske nøgle par, der kan blive oprettet, er kun brugt til adgangskodegodkendelse, ikke den krypterede forbindelse. Den symmetriske kryptering tillader selv adgangskodegodkendelse at blive bestyttet mod “snooping”.” 
 
-	Den symmetriske krypteringsnøgle skabt af denne procedure er sessions-baseret og indeholder den faktiske kryptering med den delte “secret”. Dette gøres inden godkendelse af en klient. 

•	Asymmetric Encryption
-	Asymmetrisk kryptering er forskellig fra symmetrisk kryptering ved at den når man sender date I en retning, er der brug for to nøgler. Den ene nøgle er kendt som “private key”, mens den anden nøgle er en “public key”. 
-	Den offentlige nøgle kan frit blive delt med andre. Den er associeret med pardannede nøgle, men den private nøgle kan IKKE blive udledt af den offentlige nøgle. Det matematiske forhold mellem “the private key” og “the public key” tillader den offentlige nøgle at krypterer beskeder som kun kan blive dekrypteret af den private nøgle. 
-	“The private key” bør blive holdt hemmelig og skal ikke blive delt med andre deltagere. 
-	“the private key” er den eneste component I stand til at dekrypterer beskeder som var krypteret ved brug af den associerede “public key”


•	Hashing and        MAC (Message Authentication Code)
-	Kryptografiske hashfunktioner er metoder til at skabe en kortfattet “signatur” eller resume af et sæt informationer. Deres vigtigste kendetegn er, at de aldrig er beregnet til at blive “reversed”, de er næsten umulige at påvirke forudsigeligt, og de er praktisk talt unikke. 
-	En brugere skal ikke være I stand til at producer den originale meddelelse fra en given hash, men de skal være I stand til at fortælle, om en given meddelelse producerede en given hash. 
-	Hash bruges hovedsageligt til dataintegritetsformål og til at verificere ægtheden af kommunikation. Den vigtigste anvendelse i SSH er med HMAC eller hash-baserede meddelelsesgodkendelseskoder. Disse bruges til at sikre, at den modtagne meddelelsestekst er intakt og umodificeret.
-	Autentificering ved hjælp af SSH-nøglepar begynder, efter at den symmetriske kryptering er etableret

-	Ved en SSH forbindelse bruges “public key” til at kryptere data, der kun kan dekrypteres med den private nøgle. Den offentlige nøgle kan deles frit, fordi selv om den kan kryptere for den private nøgle, er der ingen metode til at udlede den private nøgle fra den offentlige nøgle.


•	      Cipher Suites
•	Digital Signatures
•	Certificate Authorities and Certificate Trust Hierarchies

-	Teknisk set er forskellen mellem en digital signatur og digital certifikat, at et certifikat binder en digital signatur til en enhed, mens en digital signatur er at sikre, at en data / information forbliver sikker fra det sted, den blev udstedt. Med andre ord: digitale certifikater bruges til at verificere en persons (afsenders) troværdighed, mens digitale signaturer bruges til at verificere pålideligheden af de data, der sendes.

