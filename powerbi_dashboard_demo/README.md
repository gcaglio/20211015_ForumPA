Cartella contenente i file CSV di esempio che alimentano la dashboard PowerBI.
I file CSV rappresentano, in un ambito reale produttivo, un possibile output di chiamate API di integrazione verso application catalog e cmdb.


**app_catalog.csv**

Rappresenta un estratto dei dati provenienti dal catalogo applicativo.
Di seguito la descrizione dei campi:
app_id : identificativo dell'applicazione (es: K123)
app_name : nome completo dell'applicazione (es: MyCRM v12.3)
app_owner_name : nome della persona referente per l'applicazione (es: Gianni)
app_owner_surname : cognome della persona referente per l'applicazione (es: Fittizio)
app_owner_email : email della persona referente per l'applicazione (es: gianni.fittizio@inexistence.eu)
operating_hours : orario di servizio dell'applicazione (es: H24, 5x8, 7x8, ecc)

**bigfix_export_oraclelinux.csv**

Rappresenta l'output del web report di HCL BigFix contenente le patch da installare ed installate, per tutti i sistemi gestiti.
Il file, nella mia implementazione, è arricchito del campo "data" di riferimento durante l'upload nel DB di storico (quindi la data non viene presa dal file, ma dall'interfaccia di upload del file, imputata manualmente).
Di seguito la descrizione dei campi:
Data : data di riferimento (es: 2021-08-01)
Avanzamento : avanzamento applicazione patch da BigFix (percentuale)
CVE : campo CVE da BigFix (elenco dei CVE impattati)
ID origine : nome ELSA*** da BigFix
Severità origine : label rappresentante la criticità della patch, da BigFix
Conteggio computer applicabili : cumulativo, n° totale computer su cui la patch è applicabile (da BigFix)
Conteggio computer corretti : comulutaivo, n° totale computer su cui la patch è stata applicata (da BigFix) 
Nome : nome della patch, da BigFix
Computer : hostname, da BigFix
Relazione : label che rappresenta lo stato dell'applicazione della patch per questo hostname (applicata o meno), da BigFix


**rel-host-app.csv**

Rappresenta un output da cmdb con l'assegnazione di ciascun host verso l'applicazione o le applicazioni servite.
hostname : hostname (sarà usato per la join con il campo Computer dell'estrazione da BigFix bigfix_export_oraclelinux.csv)
app_id : identificativo dell'applicazione (es: K123); sarà usato per la join con il campo app_id dell'app_catalog.csv
environment : label corrispondente all'ambiente (es: produzione, pre-produzione, quality, problem-determination, sviluppo, test....)





