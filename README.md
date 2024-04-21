## Atelier 1: Osint

#### Étape 1 -> Trouver les emails de l'entreprise

J'ai décidé d'utiliser le site https://prospeo.io/domain-search pour trouver les adresses emails d'un nom de domaine spécifique dans mon cas `esiea.fr`.

<img src="https://i.imgur.com/vuFJpbk.png"  height="300"/>

<details>
  <summary>Liste complète des emails trouvés</summary>

```plaintext
felicia.ionascu@esiea.fr
ProfessionalFelicia Ionascu

amelie.chapelot@esiea.fr
ProfessionalAmelie Chapelot

jana.dittfurth@esiea.fr
ProfessionalJana Dittfurth

cedric.philippot@esiea.fr
ProfessionalCedric Philippot

alexandre.wang@esiea.fr
Generic

Alexandre Qiuping Wang

mathilde.lavelle@esiea.fr
ProfessionalMathilde Lavelle

stephanie.gellardo@esiea.fr
ProfessionalStephanie Gellardo

soto@esiea.fr
Professional
club-anciens@esiea.fr
Professional
contact@esiea.fr
Generic

marsaud@esiea.fr
Professional
accueil@esiea.fr
Professional
jerome.darugna@esiea.fr
ProfessionalJerome Darugna

fuertes@esiea.fr
Professional
sav-esieabot@esiea.fr
Professional
esieabot@esiea.fr
Professional
evelyne.klinger@esiea.fr
ProfessionalEvelyne Klinger

loic.roussel@esiea.fr
ProfessionalLoic Roussel

ca@esiea.fr
Professional
formations-securite@esiea.fr
Generic

patricia.besset-veziat@esiea.fr
Professional
drezen@esiea.fr
Professional
francois@esiea.fr
ProfessionalFrancois

olivier.lenoir@esiea.fr
ProfessionalOlivier Lenoir

anastasiia.savchenko@esiea.fr
ProfessionalAnastasiia Savchenko

admissions@esiea.fr
Generic

openesiea@esiea.fr
Professional
diego.vilelamonteiro@esiea.fr
ProfessionalDiego Vilelamonteiro

alumni@esiea.fr
Generic

filiol@esiea.fr
Professional
nuit-info@esiea.fr
Professional
projets@esiea.fr
Professional
reinbold@esiea.fr
Professional
pissochet@esiea.fr
Professional
sixtine.renard@esiea.fr
ProfessionalSixtine Renard

fatiha.gas@esiea.fr
ProfessionalFatiha Gas

laurent.huet@esiea.fr
ProfessionalLaurent Huet

vincent.guyot@esiea.fr
ProfessionalVincent Guyot

president@esiea.fr
Generic

recrutement@esiea.fr
Generic

legall@esiea.fr
Generic

guillaume.lemesle@esiea.fr
ProfessionalGuillaume Lemesle

elise.marie@esiea.fr
ProfessionalElise Marie

wassner@esiea.fr
Professional
dea@esiea.fr
ProfessionalDea

carole.clavreul@esiea.fr
ProfessionalCarole Clavreul

olena.skrypnyk@esiea.fr
ProfessionalOlena Skrypnyk

marcos.richer@esiea.fr
ProfessionalMarcos Richer De Forges

nicolas@esiea.fr
ProfessionalNicolas Ribeyre

adeline.foucault@esiea.fr
ProfessionalAdeline Foucault

```

</details>
<br/>

> Je trouve un certain nombre d'adresses emails, j'en déduis que le format d'adresse email est prenom.nom@esiea.fr.

#### Étape 2 -> Chercher des informations sur les employés

Dans cet exemple, je vais chercher des informations sur `vincent.guyot` qui est un des employés de l'entreprise.

Je vais utiliser un google site pour faire de l'OSINT trouvé sur github [https://github.com/oryon-osint/querytool](https://github.com/oryon-osint/querytool).

Pour l'utiliser il suffit de renseigner notre recherche, dans mon cas c'est `prenom.nom.esiea`.

<img src="https://i.imgur.com/veBPEX9.png" height="200"/>

Et le google sheet va structurer les liens pour nous. Google, LinkedIn, Instagram, Facebook etc.

> Google sheet accessible ici: https://docs.google.com/spreadsheets/d/1qwvThEWQTdJTxK7pJkRCQepGUdUyDrKttVunr76nZeY/edit?usp=sharing

Grâce à ce google sheet, je trouve une recherche google préconstruite qui me permet d'afficher les documents public lié à son nom, j'en ai trouvé un qui récapitule son parcours professionnel. Sachant que ce document est très intéressant puisque cette personne n'a pas de profil LinkedIn.

<img src="https://i.imgur.com/CaDocpZ.png"  height="300"/>

- Il a obtenu un master en informatique à l'École Supérieure d'Informatique Électronique et Automatique (ESIEA) à Paris en 2000.
- Il a reçu son doctorat en Réseaux et Sécurité de l'Université Pierre et Marie Curie (UPMC) à Paris en 2005.
  De 2001 à 2006, il était professeur assistant en génie électrique à l'Université de Créteil en France.
- Il est actuellement professeur associé à l'ESIEA et est responsable du Master spécialisé international en Réseaux et Sécurité Informatique.
- Il est également associé de recherche à l'Université Pierre et Marie Curie à Paris et collabore avec Télécom Paris Tech.
- Il donne des cours à l'Université de Créteil et à l'Université de Bordeaux.
- Il a co-écrit deux livres et deux autres seront publiés prochainement.
  Ses intérêts de recherche incluent la mobilité et la sécurité des réseaux, les cartes à puce et les RFID.

Après avoir essayé de trouver ses réseaux sociaux avec le google sheet, je n'ai pas trouvé de résultats pertinents. Je bascule donc sur un outil que je connais bien https://github.com/sherlock-project/sherlock.
Mais en vain. Je n'ai pas trouvé de résultats pertinents.

Je passe un peu plus rapidement sur cette partie pour me concentrer sur les autres étapes du TP.

Pour lister les subdomains j'utilise https://pentest-tools.com/information-gathering/find-subdomains-of-domain

<details>
<summary>Subdomains</summary>

```plaintext
warmup.esiea.fr	35.185.44.232
jpo.groupe.esiea.fr	35.185.44.232
analytics.esiea.fr	35.244.253.87
frallinge.esiea.fr	40.66.52.254
admissions.esiea.fr	51.15.202.91
admissions.groupe.esiea.fr	51.15.202.91
autodiscover.esiea.fr	52.98.228.40
club-secu.esiea.fr	76.76.21.123
ent.esiea.fr	82.97.11.228
e-learning.esiea.fr	83.145.86.87
mx.esiea.fr	86.64.78.41
mailhost.esiea.fr	86.64.78.41
mail.esiea.fr	86.64.78.41
bdeparis.esiea.fr	89.234.180.61
pfh-paris.esiea.fr	109.234.161.36
capprojets.esiea.fr	109.234.161.36
candidature.esiea.fr	149.62.152.87
www.recherche.esiea.fr	149.62.158.50
recherche.esiea.fr	149.62.158.50
esiea.fr	149.62.158.51
ftp.esiea.fr	149.62.158.51
embaucherh.esiea.fr	149.62.158.51
learning.esiea.fr	149.62.158.51
www.esiea.fr	149.62.158.57
en-dev.esiea.fr	149.62.158.57
dev.esiea.fr	149.62.158.57
en.esiea.fr	149.62.158.57
jpo-backend.groupe.esiea.fr	149.62.158.60
experts.esiea.fr	185.235.207.2
api.inscription.esiea.fr	185.235.207.2
www.inclusiveengineeringdays.esiea.fr	185.235.207.2
cdd-intra.esiea.fr	185.235.207.2
zammad.esiea.fr	185.235.207.2
gocapprojet.esiea.fr	185.235.207.2
pandora.esiea.fr	185.235.207.2
remote.esiea.fr	185.235.207.2
lookyloo.esiea.fr	185.235.207.2
fm-ruch.esiea.fr	185.235.207.2
evenements.esiea.fr	185.235.207.2
sand.esiea.fr	185.235.207.2
inscription-colloque.esiea.fr	185.235.207.2
misp.esiea.fr	185.235.207.2
moodle-bas.esiea.fr	185.235.207.2
inge.esiea.fr	185.235.207.2
techday-paris.esiea.fr	185.235.207.2
bw.esiea.fr	185.235.207.2
steak-hashe.esiea.fr	185.235.207.2
my.esiea.fr	185.235.207.2
rimbaud.esiea.fr	185.235.207.2
info.esiea.fr	185.235.207.2
inclusiveengineeringdays.esiea.fr	185.235.207.2
maquette.esiea.fr	185.235.207.2
centreon.esiea.fr	185.235.207.2
maquette2425.esiea.fr	185.235.207.2
inscription.esiea.fr	185.235.207.2
sic.esiea.fr	185.235.207.2
maquette2324.esiea.fr	185.235.207.2
cve2attack.esiea.fr	185.235.207.2
malware-lab.esiea.fr	185.235.207.2
ruch.esiea.fr	185.235.207.2
eon.esiea.fr	185.235.207.2
kps.esiea.fr	185.235.207.2
cron-healthchecks.esiea.fr	185.235.207.2
back.inscription.esiea.fr	185.235.207.2
paam.esiea.fr	185.235.207.2
vote-esiealumni.esiea.fr	185.235.207.2
portail.esiea.fr	185.235.207.2
ir-seb.esiea.fr	185.235.207.2
scolarite-sud.esiea.fr	185.235.207.2
maquette2223.esiea.fr	185.235.207.2
pairse.esiea.fr	185.235.207.2
wei.esiea.fr	185.235.207.2
webu4.esiea.fr	185.235.207.2
techday-experts.esiea.fr	185.235.207.2
ese.esiea.fr	185.235.207.2
dumas.esiea.fr	185.235.207.2
edt.esiea.fr	185.235.207.2
gala.esiea.fr	185.235.207.2
api.eon.esiea.fr	185.235.207.2
openlab.esiea.fr	185.235.207.2
api.esiea.fr	185.235.207.3
triolet.esiea.fr	185.235.207.4
bbb.esiea.fr	185.235.207.5
broker.netmaker.esiea.fr	185.235.207.6
dashboard.netmaker.esiea.fr	185.235.207.6
turnapi.netmaker.esiea.fr	185.235.207.6
api.netmaker.esiea.fr	185.235.207.6
turn.netmaker.esiea.fr	185.235.207.6
dumas-test.esiea.fr	185.235.207.20
support.esiea.fr	185.235.207.22
registry.esiea.fr	185.235.207.37
gitlab.esiea.fr	185.235.207.37
esieaouestradio.esiea.fr	185.235.207.38
vizer.esiea.fr	185.235.207.38
webadmin.esiea.fr	185.235.207.38
kidsprofiler.esiea.fr	185.235.207.38
covoiturage.esiea.fr	185.235.207.38
fusion.esiea.fr	185.235.207.38
air.esiea.fr	185.235.207.38
francois.esiea.fr	185.235.207.38
nef2.esiea.fr	185.235.207.38
open.esiea.fr	185.235.207.57
```

</details>
<br/>

Liste et position des employés consultables depuis [Linkedin](https://www.linkedin.com/search/results/people/?currentCompany=%5B%2226559%22%5D&origin=COMPANY_PAGE_CANNED_SEARCH&sid=Uz7) il suffit de faire le lien entre les noms et les adresses emails trouvées précédemment.

<img src="https://i.imgur.com/7iLvr1B.png"  height="300"/>

Pour la liste des campus rien de sorcier, je suis allé sur esiea.fr.

<img src="https://i.imgur.com/dmWvd8Q.png"  height="300"/>

- Le campus ESIEA de Paris/Ivry-sur-Seine
- Le campus ESIEA de Laval
- Le campus ESIEA d'Agen
- Le campus ESIEA de Dax

J'ai pas réussi l'intégralité pour la simple et bonne raison que il y a certains points qui sont compliqués à appronfondir sans passer des heures dessus. Je préfère passer à l'étape suivante.
Et j'ai préféré me concentrer sur un profil (vincent guyot) plutôt qu'un groupe pour rendre le travail plus complet et intéressant.

## Atelier 2: Container chiffré

<img src="https://i.imgur.com/gdgB4N9.png"  height="250"/>

<img src="https://i.imgur.com/y65TCLJ.png"  height="250"/>

## Atelier 3: Full Disk Encryption

J'ai eu des difficultés à configurer le chiffrement de disque complet sur Windows. J'ai essayé de le faire sur une machine virtuelle mais j'ai eu des problèmes de compatibilité avec le matériel virtuel.

J'ai donc pris la décision de le faire sur une clef USB à la place.

La configuration de BitLocker est assez simple, il suffit de suivre les étapes.

<img src="https://i.imgur.com/BjnjxmT.png"  height="100"/>

Une fois le disque chiffré, pour déchiffrer la clef, il suffit de rentrer le mot de passe configuré.

<img src="https://i.imgur.com/EQS1844.png"  height="150"/>

Une fois le mot de passe rentré, le disque est déchiffré et accessible. Dans mon cas il y a un simple fichier texte.

<img src="https://i.imgur.com/Eoc6nu3.png"  height="200"/>

## Atelier 4: Récupération de données

Je réussi avec succès à récuperer des données supprimées, après avoir fait un formatage rapide du périphérique.

<img src="https://i.imgur.com/JJ4y5kR.png"  height="200"/>

Et après formatage complet du périphérique, aucune donnée n'est récupérable.

<img src="https://i.imgur.com/Vg0uzjq.png"  height="50"/>

> Je stop à 65% parce que le processus est très long sur mon pc. Je passe à l'étape suivante.

## Atelier 5: The Onion Router

Configuration de tor sur firefox, depuis une VM debian.

<img src="https://i.imgur.com/drSGe9z.png"  height="200"/>

Capture des requêtes DNS après avoir visité lemonde.fr, on peut constater qu'il y a des fuites DNS avec Wireshark.

<img src="https://i.imgur.com/iW3fBHh.png"  height="300"/>

Par la suite après avoir installé tor browser, je n'ai plus de fuites DNS.

<img src="https://i.imgur.com/be9zFik.png"  height="300"/>

#### Utilisation de Tails

Initialisation de la VM

<img src="https://i.imgur.com/WKsbv2s.png">

#### Installation de apache2

Configuration du port

<img src="https://i.imgur.com/kIAKebg.png"  height="300"/>

Modification du fichier index.html

<img src="https://i.imgur.com/iHEHfSg.png"  height="300"/>

#### Mon premier .onion

Modification du fichier torrc

<img src="https://i.imgur.com/IAC41i0.png"  height="300"/>

En ouvrant le .onion dans le navigateur tor, de tails, je vois bien le contenu de mon site.

<img src="https://i.imgur.com/hdg6h9v.png"  height="300"/>

Je n'ai pas pu tester des sites d'autres camarades.

## Atelier 6: GNU Privacy Guard

Après m'être cassé la tête sur Linux j'ai demandé à des collègues et je suis parti sur Kleopatra.

<img src="https://i.imgur.com/v03OdvU.png"  height="300"/>

Voici ma clé publique

<img src="https://i.imgur.com/ttBzRhl.png"  height="250"/>

Sur Kleopatra, j'ai généré une paire de clés, j'ai exporté ma clé publique et je l'ai envoyé à un collègue et récupéré la sienne.

> Nous sommes le 19/04 - 18:39, j'attends actuellement une réponse d'un collègue du groupe de classe pour tester l'envoi de fichier chiffré.

#### Déchiffrement

> 21/04 - 17:27, j'ai reçu un fichier chiffré de la part de mon collègue, je vais le déchiffrer.

De son côté mo collègue a importé ma clef et a chiffré un fichier avec sa clef en autorisant ma clef publique à accéder au fichier.

<img src="https://i.imgur.com/LQgCXp4.png"  height="300"/>

Étant donné que j'ai sa signature, j'ai la possibilité de déchiffrer son fichier.

<img src="https://i.imgur.com/XH0Umq5.png"  height="100"/>

J'ai désormais accès au fichier déchiffré.
