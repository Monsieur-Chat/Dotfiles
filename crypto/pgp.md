**PGP**
[gpg --help]

La clé publique est utilisée pour signer et certifier.
La sous-clé est utilisée pour chiffrer.

en minuscule -k = clé publique
en MAJUSCULE -K = clé privée/secrète
-a = format ASCII
-b = format binaire

* __Genérer une clé maitre__
gpg --full-generate-key 

"gpg --edit-key [id clé / mail ]" ouvre un shell gpg
  addkey = créer la sous-clé
  save 

* __Révocation de certificat__
Lors de la création de la clé, le chemin du certificat de révocation est indiqué.

* __Afficher les clés__
gpg --list-keys / -k / --list-secret-keys / -K
* __Afficher les signatures__
gpg --list-signature
* __Exporter des clés__
gpg -b --export-secret-key [uid-clé / mail] > /chemin/fichier  
gpg -a --export-secret-key [uid-clé / mail] > /chemin/fichier  
* __Effacer les clés__
gpg --delete-secret-and-public-keys
* __Importer des clés__
gpg --import nom-fich.truc

* __Récuperer une clé depuis un serveur de clé__
gpg --keyserver key-server.rt.iut-acy.local -rec-keys [id-clé]
* __Signer une clé__
gpg --sign-key [id-clé / mail]
* __Upload une clé__
gpg --send-keys --keyserver key-server.rt.iut-acy.local [id-clé]

__Modifier la confiance d'une clé importée__
gpg --edit-key
>trust

__Chiffrer un doc__
gpg -e -v [uid/mail] texte.txt (-a) > texte.txt.gpg
__Dechiffrer__
- le déchiffrement utilise notre clé privée, on en a qu'une en général donc on a rien besoin de préciser.
gpg -d texte.txt.gpg > texte-dech.txt

__Signer un document__
gpg --sign fichier.txt > fichier = message signé et compressé
gpg --clearsign fichier.txt > fichier = message + signature
gpg --detach-sign fichier.txt > fichier = signature
__Verifier la signature__
gpg --verify fichier-signé 
