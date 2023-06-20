Questa è una simulazione di attacco realizzata come progetto per il corso di Sicurezza Informatica del CdL di Informatica e Comunicazione Digitale (Università degli Studi di Bari). Tutti gli script sono stati utilizzati in rete locale, in un ambiente controllato, per scopi didattici. Non si assume alcuna responsabilità per eventuali utilizzi delle tecnologie adoperate.
Scenario:
"Un nostro amico stretto, ex dipendente di un’azienda, è stato vittima di un licenziamento illegittimo, nonostante abbia provato a “difendersi” tramite contestazione e difesa. Data la sua rabbia, si è rivolto a noi per chiederci aiuto ad effettuare una piccola “vendetta”.
Essendo un ex dipendente, egli ci ha fornito varie informazioni riguardo l’azienda, e soprattutto riguardo le macchine utilizzate, ossia:
● Versione del Sistema Operativo utilizzato dalle macchine.
● Password per usufruire del wi-fi.
● Informazioni su Firewall
La vittima in questo caso è l’azienda stessa (con tutte le sue macchine), ma in questa simulazione verrà attaccata una sola di queste macchine. Essendo una piccola azienda, molto probabilmente considera la cybersecurity un dipiù non
necessario ai fini dell’operatività del business e per questo risulta molto probabilmente un soggetto vulnerabile. L’attaccante utilizzerà una macchina Kali Linux per accedere al sistema della vittima. Quest’ultima, invece, utilizzerà la versione di Windows 10 19.03 V2. Poiché si tratta solo di una simulazione di attacco, sono state utilizzate sulla stessa rete due macchine virtuali aventi i sistemi operativi sopra citati."

L’attacco sfrutta un difetto del protocollo SMB 3.1.1(Server Message Block)
presente in alcune versioni di Windows 10 e Windows Server:
● Windows 10 Version 1903 (32-bit, ARM64, x64)
● Windows 10 Version 1909 (32-bit, ARM64, x64)
● Windows Server, version 1903
● Windows Server, version 1909
Questa vulnerabilità consente a un pacchetto di dati, creato appositamente per sfruttare la vulnerabilità, di funzionare sul server SMB centrale ed eseguire codice casuale sul sistema. Questa vulnerabilità è stata registrata come <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-0796">CVE 2020-0796</a> e ha ricevuto un punteggio di pericolosità di 10 su 10.
In questo attacco si andrà a sfruttare questa vulnerabilità per creare una reverse-shell sulla macchina della vittima. Si andrà poi a trasferire su di essa un file eseguibile malevolo e, tramite una ulteriore powershell reverse-shell, si andrà ad eseguirlo, andando a criptare tutti i file presenti sulla macchina.
L’attacco risulterà molto simile ad un attacco Ransomware, con la sola differenza che non ci sarà nessuna richiesta di denaro per avere i propri file decriptati.
