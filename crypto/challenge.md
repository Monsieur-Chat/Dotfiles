**Challenge : chiffrer avec une clé privée**
1- Créer clé privée
openssl genrsa -out mykey.pem 1024

2- Séparer clé privée/clé publique
openssl rsa -in mykey.pem -pubout -out mykeypub.pem

3- Chiffrer la clé privée
openssl rsa -algo -in mykey.pem -out mykey.pem

4- Crypter 
openssl rsault -encrypt -in essay.txt -inkey mykeypub.pem -pubin -out jax.txt

5- Décrypter
openssl rsault -decrypt -inkey mykey.pem -in jax.txt -out al.txt

6- Calculer empreinte 
openssl dgst -sha1 -out empreinte video

7- signer document
openssl rsault -sign -in empreinte  
 - Verifier 
openssl dgst -sha1 -verify mykeypub?pem -signature signature jay.txt

8- Crypter un gros fichier
openssl enc -e -algo -in fich -out fich
            -d
