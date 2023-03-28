**Openssl**
[openssl help]

-iv = Vecteur d'initialisation hexadecimal
-K = clé hexadecimale

__Chiffrer__
openssl enc -algo -in fich -out fich-enc (-pass pass:mdp)
openssl enc -algo -in fich -out fich-enc -iv 123ABC -K 0123ABCD
__Dechiffrer__
openssl enc -d -algo -in fich.dat -out fich-dec 

__Codage et decodage__
openssl enc (-d) -base64 -in B64.txt -out B64.dec.txt
__Créer une chaine de 128b et l'encoder en base64__
openssl rand -base64 128

__Hachage__
openssl dgst-list
openssl dgst -algo fich.txt > fich-hach.txt

Comparer la taille : hexedit nom-fich

__Gen paire de clé asymétrique (2048 bits)__
openssl genrsa -algo -out clepriv.pem 2048
openssl rsa -in clepriv.pem -pubout -out clepub.pub
__Afficher la clé en décodé__ : -text
openssl rsa -in clepriv.pem -noout -text

__Chiffrer avec une clé publique__
openssl rsault -encrypt -in fich.txt clepub.pub -pubin -out fichchiff.txt
__Transmettre msg chiffré__
openssl rsault -decrypt -in fichchiff.txt -inkey clepriv.pem -out sortie
