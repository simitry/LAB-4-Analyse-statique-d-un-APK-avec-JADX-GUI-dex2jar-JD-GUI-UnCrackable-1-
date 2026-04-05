# LAB-4-Analyse-statique-d-un-APK-avec-JADX-GUI-dex2jar-JD-GUI-UnCrackable-1

# Mini rapport

Titre : Analyse statique de Uncrackable1
Date : 04/05/2026
Analyste : MAKKOUCH Saad
APK : Uncrackable1, version 1.0
Provenance : https://mas.owasp.org/crackmes/Android/
Outils utilisés : JADX GUI v1.5.5, dex2jar v2.0, JD-GUI v1.6.6

# vérifier l'APK

<img width="603" height="48" alt="image" src="https://github.com/user-attachments/assets/26cd663c-905d-4d21-bcce-8fc19512cb14" />


<img width="693" height="880" alt="image" src="https://github.com/user-attachments/assets/b691a22e-7283-403d-8dce-a5a57c5b24ab" />


## lister le contenu de l'apk

<img width="411" height="31" alt="image" src="https://github.com/user-attachments/assets/8b251719-dba0-40d7-b743-faeb6a740812" />
l'image ci-dessus charge la bibliotheque de compression

<img width="528" height="34" alt="image" src="https://github.com/user-attachments/assets/6e8ee2a1-6b63-4860-b032-b944031ea6d9" />
definition du chemin de l'apk

<img width="599" height="49" alt="image" src="https://github.com/user-attachments/assets/494c2cf5-3025-436c-b40f-beaba61a9437" />
verifie l'existance du fichier de l'apk

<img width="863" height="26" alt="image" src="https://github.com/user-attachments/assets/96238c46-7731-4d43-ba0e-252505df5e0a" />
<img width="415" height="236" alt="image" src="https://github.com/user-attachments/assets/b7418423-8e3a-4989-b794-f542aa191ce5" />
lecture du contenu de l'apk

## Calculez le hash de l'APK pour traçabilité

<img width="460" height="26" alt="image" src="https://github.com/user-attachments/assets/372f185b-8165-4260-9a21-bfc4ce8bf266" />
<img width="678" height="77" alt="image" src="https://github.com/user-attachments/assets/d2dafd26-e45e-4f1a-98ec-0f8e9f4faef6" />

## Vérifiez la signature de l'APK

<img width="1582" height="328" alt="image" src="https://github.com/user-attachments/assets/7a5790b4-0364-4bc4-80f3-ecea0a510377" />
ici dans cette commande j'ai ajouté " --print-certs "juste pour voir les details du certificat.

# Extraire/obtenir l'apk 
<img width="424" height="80" alt="image" src="https://github.com/user-attachments/assets/f3f65356-110c-44a9-ae6c-7caaa5a131a6" />

on genere l'apk , aprèes je lance l'apk dans Pixel 6 

<img width="479" height="969" alt="image" src="https://github.com/user-attachments/assets/31849a81-ed57-4990-a51a-236e822034bb" />

# analyse avec JADX GUI

## on lance JADX GUI

<img width="565" height="65" alt="image" src="https://github.com/user-attachments/assets/ce4deae4-f803-4c57-b543-0fa1408beb55" />

en utilisant jadx gui on peut voir le code source de l'apk
<img width="1323" height="745" alt="image" src="https://github.com/user-attachments/assets/05391551-75d5-470f-be43-eef5b3e0efd4" />
<img width="1330" height="742" alt="image" src="https://github.com/user-attachments/assets/6cc00d14-ed69-44ab-b24a-e9ec0feb5cc5" />


dans le manifeste on peut trouver plus d'info sur l'app
<img width="1333" height="750" alt="image" src="https://github.com/user-attachments/assets/09fd4c35-4305-46b2-9713-51a12cac3951" />

on analysant le manifest, on peut voir le nom du package principal ("owasp.mstg.uncrackable1"), nom de version, min sdk, target sdk, ce qu'on constate aussi est il n'y a pas "uses-permission" cela veut dire que l'apk ne demande aucune permission android


# Recherche de chaînes sensibles

on utilise la fonction de recherche pour chercher quelque chaine sensible comme par exemple "https://" , "api", "api_key", "DEBUG"


<img width="1374" height="739" alt="image" src="https://github.com/user-attachments/assets/2d48c9c5-c40d-4c84-8288-3162815fff57" />
<img width="1167" height="486" alt="image" src="https://github.com/user-attachments/assets/d5b36044-0e7a-4de0-8eb9-0228113cbc4d" />

dans le deuxième screenshot, on a trouve quelque resultat en cherchant "secret" ce qui peut etre critique pour la securité de l'app 

## Convertir DEX en JAR avec dex2jar

Extraction et verification des fichier dex de l'apk

<img width="1083" height="436" alt="image" src="https://github.com/user-attachments/assets/bf7fa0ee-590c-4d28-931f-32bb828a305f" />

Convertission de chaque fichier dex en jar

<img width="878" height="304" alt="image" src="https://github.com/user-attachments/assets/70d02928-ce34-492d-ab6a-2406b33dcf33" />


# Comparaison JADX vs JD-GUI

<img width="928" height="716" alt="image" src="https://github.com/user-attachments/assets/dac76100-183e-45f9-9f51-91b0ce3440ee" />

en comparant les deux classes (a.class) je constate que le nom des variable change, jadx donne plus d'information sur l'apk (structure complete: android manifest ....) et facile pour naviger et trouver les variables

# cracker la clé

on ouvre un nouveau projet dans android studio avec le code source de l'apk,puis on ajoute cette ligne pour voir la clé
<img width="708" height="67" alt="image" src="https://github.com/user-attachments/assets/4c18134e-9437-4688-87ab-ac68b62b1f09" />

<img width="1032" height="87" alt="image" src="https://github.com/user-attachments/assets/8f98585c-9e95-4f19-834c-3c09b2e71b62" />


<img width="436" height="879" alt="image" src="https://github.com/user-attachments/assets/b68c7174-6036-4174-b4c1-7a82c848a969" />









 












