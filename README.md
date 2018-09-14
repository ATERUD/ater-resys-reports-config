# ater-resys-reports-config

Alcune istruzioni per automatizzare il processo di deploy dei report:


### Installazione iniziale

Posizionarsi in un percorso locale (es. C:\reports)

Effettuare il clone dei repository:

```sh
$ cd  C:\reports\
$ git clone https://github.com/ATERUD/ater-resys-reports-bandi-domande-incommissione.git

$ git clone https://github.com/ATERUD/ater-resys-reports-bandi-graduatorie-provvisoriaalfabetica.git
$ git clone https://github.com/ATERUD/ater-resys-reports-bandi-domande-permanenzainregione.git
$ git clone https://github.com/ATERUD/ater-resys-reports-bandi-graduatorie-provvisoria.git
$ git clone https://github.com/ATERUD/ater-resys-reports-bandi-graduatorie-definitivaalfabetica.git
$ git clone https://github.com/ATERUD/ater-resys-reports-bandi-graduatorie-definitiva.git
$ git clone https://github.com/ATERUD/ater-resys-reports-bandi-graduatorie-cambialloggioalfabetica.git
$ git clone https://github.com/ATERUD/ater-resys-reports-bandi-graduatorie-provvisoria.git
$ git clone https://github.com/ATERUD/ater-resys-reports-bandi-graduatorie-cambialloggioalfabetica.git
$ git clone https://github.com/ATERUD/ater-resys-reports-bandi-graduatorie-cambialloggio.git
$ git clone https://github.com/ATERUD/ater-resys-reports-config.git

```


### Creazione dei file .zip 
Posizionarsi in un percorso locale (es. C:\reports)

Eseguire il comando Powershell.exe per ogni repository
```sh
Deploy-Zip.ps1 [-pathDestinationFile <string>] [-overWriteDestinationFile <string>] [<CommonParameters>]
```
vedere esempio pratico:
```sh
cd C:\reports\ater-resys-reports-bandi-domande-incommissione\
Powershell.exe -File Deploy-Zip.ps1 -overWriteDestinationFile true -pathDestinationFile "C:\reports\"
```
Il comando genera il file .zip del report che dovrà essere caricato sul portale [ResysWeb](http://bandi-ater-pordenone-rs.regione.fvg.it/ReSysWeb/).

In ogni Repository è presente un README.md dove viene descritto come deve essere caricato il file e relative descrizioni dei campi.


### Todos
 - Aggiungere pià documentazione
 - Implementare la creazione dinamica del README.md
 - Durante il deploy fare in modo che il README.md venga aggiornato in maniera batch.