# GUIDb
progetto in collegamento con database

Creazione di un nuovo progetto .NET:
-Apri Visual Studio o l'IDE di tua scelta e crea un nuovo progetto .NET.

Aggiunta del pacchetto sqlite-net-pcl:
-Nel tuo progetto, aggiungi il pacchetto "sqlite-net-pcl" utilizzando il package manager o il file di configurazione del progetto (ad esempio, il file .csproj).
-Assicurati che la versione del pacchetto sia compatibile con la tua versione di .NET.
![Immagine 2023-05-16 171428](https://github.com/AgoRoss/GUIDb/assets/116869835/43ff3380-2e14-4a3d-976c-07345db96e0f)

Creazione delle cartelle di destinazione:
-Nella soluzione del tuo progetto, crea una cartella chiamata "raw" per contenere il file "chinook.db".
-Crea anche una cartella chiamata "Local Data" per copiare il file "chinook.db" durante l'esecuzione del programma.

Aggiunta del file chinook.db:
-Scarica il file "chinook.db" da una fonte affidabile.
-Sposta il file "chinook.db" nella cartella "raw" del tuo progetto.

Codice C# per copiare il file nella cartella "Local Data":
-Aggiungi un blocco di codice C# nella classe principale del tuo programma (ad esempio, nel metodo Main).
-Utilizza il seguente codice per copiare il file "chinook.db" nella cartella "Local Data" durante l'esecuzione del programma:

```csharp
Copy code
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        string sourceFilePath = Path.Combine("raw", "chinook.db");
        string destinationFolderPath = "Local Data";

        string destinationFilePath = Path.Combine(destinationFolderPath, "chinook.db");

        if (!Directory.Exists(destinationFolderPath))
        {
            Directory.CreateDirectory(destinationFolderPath);
        }

        File.Copy(sourceFilePath, destinationFilePath, true);

        Console.WriteLine("File chinook.db copied to Local Data folder.");
    }
}
```

Utilizzo della libreria sqlite-net-pcl per accedere al database:
-Utilizza la libreria sqlite-net-pcl nel tuo progetto per accedere al file "chinook.db" nella cartella "Local Data" e interagire con il database SQLite.
-Puoi trovare la documentazione e gli esempi di utilizzo della libreria sul sito ufficiale.
