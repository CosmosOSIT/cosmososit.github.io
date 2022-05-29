# Installazione
### Prerequisiti
- Visual Studio 2022 - [Scarica](https://my.visualstudio.com/Downloads?q=visual%20studio%202019&wt.mc_id=o~msft~vscom~older-downloads)
- Workload .NET di Visual Studio 2022 (selezionare anche .NET 5.0)
- .NET Framework versione 4.8 Developer pack [Scarica](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net48)
- VMware player o workstation - [Scarica](https://www.vmware.com/it/products/workstation-player/workstation-player-evaluation.html) - la versione Player è raccomandata perché è gratis.

### Installazione di Cosmos
Innanzitutto, è necessario scegliere tra User Kit e Dev Kit. Si consiglia ai nuovi utenti di iniziare con lo User Kit, ma di passare successivamente al Dev Kit solo se sono necessarie le funzionalità più recenti e si desidera contribuire nuovamente al progetto principale. Il Dev Kit è la sorgente live contro cui il Cosmos Team si sviluppa direttamente. Il Dev Kit ha le funzionalità più recenti e più grandi, ma in vari momenti ha problemi noti e talvolta potrebbe anche non essere compilato. Pertanto, per utilizzare il Dev Kit, assicurati di unirti ai nostri canali di supporto e di informarti sullo stato corrente prima di utilizzare il Dev Kit o aggiornarlo.

Lo User Kit è una versione stabile istantanea di Cosmos che include un programma di installazione predefinito. Lo UserKit tuttavia è spesso un po 'obsoleto rispetto al DevKit e viene aggiornato solo occasionalmente. Lo User Kit è un ottimo modo semplice per familiarizzare con Cosmos, ma gli sviluppatori attivi dovrebbero passare al Dev Kit dopo aver acquisito molta familiarità con lo UserKit e aspettarsi alcuni bug qua e là.

### Kit utente
Scarica l'ultima versione di Cosmos dai [rilasci](https://github.com/cosmosos/cosmos/releases) (scarica il file exe)
Attendere il completamento del download, quindi eseguire il programma di installazione. Consenti l'esecuzione come amministratore. Assicurati che VS2019 NON sia in esecuzione quando lo fai.
Fai clic su "Avanti", quindi su "Installa"
Attendere l'avanzamento dell'installazione. Mancia: Alla fine l'installatore potrebbe sembrare in stallo, ma sta ancora facendo qualcosa in background. ATTENDI che il pulsante "Fine" diventi disponibile.
Cosmos dovrebbe ora essere installato. Segui altri tutorial per scoprire come creare il tuo primo sistema operativo.
Kit di sviluppo
Prerequisiti aggiuntivi
Carico di lavoro di Visual Studio 2019: sviluppo di estensioni di Visual Studio
Inno Quick Start Pack (gratuito) - Installa con impostazioni predefinite, mantieni selezionata l'opzione Preprocessore - [Scarica](https://jrsoftware.org/isdl.php#qsp)
.NET Core 5.0 SDK - [Download](https://dotnet.microsoft.com/en-us/download/dotnet/5.0)
Ottieni la fonte
Cosmos source è ospitato su GitHub. Il metodo più semplice per ottenere la fonte è scaricare un file .zip, tuttavia questo rende l'aggiornamento e l'ottenimento degli ultimi aggiornamenti un po 'complicato.
Per aggiornare l'origine Cosmos in modo più efficiente, utilizzare la riga di comando Git o una delle numerose interfacce utente Git. Qualsiasi frontend può funzionare correttamente, ma per gli utenti nuovi a Git, suggeriamo GitHub Desktop. Per gli utenti Git più esperti, ci piace molto Git Kraken. Git Kraken è gratuito per uso non commerciale come Cosmos. Sono disponibili anche SourceTree, Git GUI e altri.

Per aiutare a migliorare l'incapsulamento e per invitare più sviluppatori ad assistere in varie aree, Cosmos è diviso in quattro repository Git. Ognuno di questi è progettato per essere un progetto indipendente, anche se Cosmos si basa sugli altri tre.
Sarà necessario estrarre l'origine per tutti e quattro i repository e devono esistere in directory di pari livello, come illustrato nel diagramma seguente. La directory di base cosmos può essere denominata qualsiasi cosa ed esistere ovunque. Ma le directory al suo interno devono corrispondere esattamente.

Windows non fa distinzione tra maiuscole e minuscole per i file, ma molti dei file . NET Core utilizzati per compilare fanno distinzione tra maiuscole e minuscole anche in Windows per i percorsi di file. Assicurati di creare le sottodirectory esattamente come mostrato. A scopo dimostrativo, supponiamo che si utilizzerà c:\source\Cosmos per eseguire l'installazione.
Questa directory di base è denominata directory Cosmos. Ciascuno dei quattro repository deve quindi essere clonato o estratto nella sottocartella corrispondente della directory Cosmos. Utilizzando questo esempio, la configurazione dovrebbe essere simile alla seguente:

c:\\source\\CosmosOS\\

c:\\source\\CosmosOS\\Cosmos\\ - [Git Repository for Cosmos](https://github.com/CosmosOS/Cosmos) 

c:\\source\\CosmosOS\\IL2CPU\\ - [Git Repository for IL2CPU](https://github.com/CosmosOS/IL2CPU) 

c:\\source\\CosmosOS\\XSharp\\ - [Git Repository for XSharp](https://github.com/CosmosOS/XSharp) 

c:\\source\\CosmosOS\\Common\\ - [Git Repository for Common](https://github.com/CosmosOS/Common) 


Stiamo lavorando per semplificare la sincronizzazione del codice. Abbiamo già sperimentato con i sottomoduli Git, tuttavia il semplice uso dei sottomoduli presenta alcuni problemi, ma il più grande di essi è che innescano uno spettacolo pirotecnico di problemi ed errori in ogni interfaccia utente Git che abbiamo provato e avrebbe limitato le opzioni degli sviluppatori e li avrebbe costretti alla riga di comando nella maggior parte dei casi. Attualmente stiamo indagando sui sottoalberi.

Per ora, è molto più facile gestire i 4 repository poiché la maggior parte delle volte, i nuovi sviluppatori di Cosmos potrebbero dover lavorare solo nel repository Cosmos. Solo quando si è a proprio agio con il concetto di sviluppo del sistema operativo e C # si dovrebbe avventurarsi in IL2CPU e XSharp.

Se si desidera mantenere aggiornata l'origine con un metodo con un clic, incollare questo codice in un file .bat nella cartella CosmosOS (come mostrato nell'esempio precedente). Questo file .bat funzionerà solo dopo che i repository sono stati clonati con git almeno una volta.

```cmd
cd C:\XSharp
git pull
cd .. \IL2CPU
git pull
cd .. \Cosmos
git pull
cd .. \Common
git pull
cd ..
```

Creazione e installazione
(se hai già installato) Se hai modificato l'origine Cosmos DevKit utilizzando Cosmos.sln o Test.sln, assicurati di impostare la configurazione della soluzione su Debug x86.

Assicurarsi che Visual Studio NON sia in esecuzione.
Nella directory principale dei file DevKit scaricati in precedenza, eseguire .install-VS2022.bat
Attendere l'avanzamento dell'installazione. (Suggerimento: alla fine l'installatore potrebbe sembrare in stallo, sta ancora facendo qualcosa, solo in background)
È ora possibile apportare modifiche agli assiemi principali di Cosmos. Se non lo si desidera, è possibile chiudere questa finestra VS e creare un nuovo progetto Cosmos come con il kit utente.
Buon Cosmos-are!
