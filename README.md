# Lhyperloader
A high-performance Kernel Driver Loader written in Rust using KDU and Manual Mapping techniques for educational research
🚀 LHYPERLOADER: The Silent Kernel Guardian
LHYPERLOADER est un utilitaire de recherche en sécurité conçu pour charger des drivers non signés dans le noyau Windows sans compromettre l'intégrité globale du système. Contrairement aux méthodes obsolètes, cet outil utilise le Manual Mapping via KDU pour une exécution "Ghost" en mémoire vive.

🏰 La Métaphore : Une Seule Place sur le Trône
Pour comprendre pourquoi cet outil est nécessaire, imaginez le noyau de votre processeur comme un Trône :

La Boîte (HVCI) : C'est la protection par défaut de Windows. Elle occupe le trône.

La Clé (DSE) : C'est ce qui verrouille la porte du château (le noyau).

Le Problème : On ne peut pas avoir deux rois sur le même trône. Pour installer notre propre moteur de virtualisation, nous sommes obligés de retirer la boîte de Windows (HVCI OFF).

L'avantage LHYPERLOADER : * Les autres outils cassent la boîte ET jettent la clé (DSE OFF permanent).

Mon loader retire la boîte (HVCI OFF) car c'est une obligation technique, mais il referme la porte à clé (DSE ON) immédiatement après avoir placé notre moteur. Votre système reste protégé des intrus extérieurs.

🛠️ Caractéristiques Techniques
🦀 Built with Rust : Gestion de la mémoire ultra-sécurisée et performances de haut niveau.

⚡ KDU Integration : Exploitation de vulnérabilités de drivers légitimes (MSI, Intel, etc.) pour pénétrer le Kernel.

👻 Manual Mapping : Chargement direct en RAM. Aucune modification du registre ou du "Audit Mode", laissant Zéro Trace sur le disque.

🖥️ Egui Interface : Une interface utilisateur fluide, moderne et réactive.

🔍 Auto-Diagnostic : Détection intelligente du constructeur CPU (Intel/AMD) et de l'état du HVCI.

🚀 Installation & Utilisation
Prérequis
Désactiver HVCI : Allez dans Sécurité Windows > Isolement du noyau et désactivez l'Intégrité de la mémoire.

Exclusion Antivirus : Ajoutez une exclusion pour le dossier du loader (l'antivirus peut rester activé pour le reste du système).

Mode d'emploi
Téléchargez la dernière version dans l'onglet Releases.

Lancez Lhyperloader.exe en tant qu'Administrateur.

Cliquez sur 🔄 Diagnostiquer pour vérifier votre compatibilité.

Sélectionnez un driver vulnérable dans la liste.

Cliquez sur 🚀 Désactiver DSE, chargez votre driver, puis réactivez la protection.

📊 Informations de Développement
Le projet est structuré pour être modulaire :

core.rs : Gère l'extraction des ressources KDU, la manipulation du registre et les appels sc pour le contrôle des services.

main.rs : Gère la boucle de rendu egui et la communication asynchrone entre les threads système et l'UI.

⚠️ Disclaimer Éducatif
Note : Ce projet est réalisé exclusivement à des fins éducatives et de recherche en sécurité informatique. L'auteur n'est pas responsable d'une utilisation abusive ou illégale de cet outil. L'utilisation de drivers Kernel comporte des risques de stabilité (BSOD) ; testez toujours dans un environnement contrôlé (VMware).

🤝 Soutenir le Projet
Si vous aimez mon travail et les explications sur le Kernel, n'oubliez pas de mettre une ⭐ Star sur ce dépôt et de vous abonner à la chaîne YouTube !
