# 🧭 Guide Fondamental et Construction de Drones

![Digital Bridge RDC](images/dBlogo.png)

## I. 🚀 Introduction aux Drones

### Qu'est-ce qu'un drone ?
- Un drone (UAV) est un aéronef sans pilote à bord.
- Il est contrôlé via des signaux radio, des ordinateurs embarqués ou des missions préprogrammées.

### Types de Drones par Utilisation :
| Type                   | Description                          | Applications                            |
|------------------------|--------------------------------------|-----------------------------------------|
| **Drones Caméra**      | Stables, avec GPS, pour filmer.      | Cinéma, inspections, cartographie.      |
| **Drones FPV**         | Pilotage en vidéo en temps réel.     | Course, freestyle, vol en intérieur.    |
| **Drones Autonomes**   | Missions guidées par IA ou GPS.      | Agriculture, livraison, secours.        |
| **À Aile Fixe/VTOL**   | Haute efficacité, longue autonomie.  | Topographie, missions longue distance.  |

### Types de Châssis :
| Forme du Châssis   | Utilisation Idéale | Description                              |
|--------------------|---------------------|------------------------------------------|
| **X-frame**        | FPV freestyle        | Moteurs symétriques autour du centre.    |
| **Deadcat**        | Cinématographie      | Bras avant plus larges, sans hélices à l’image. |
| **H-frame**        | Course               | Compact et très rigide.                  |
| **Toothpick/Micro**| Intérieur/léger      | Très léger, minimal.                     |
| **Cinewhoop**      | Vidéo en intérieur   | Caréné pour voler près des obstacles.    |

## II. 📦 Aperçu des Composants du Drone

| Composant              | Rôle                                                 |
|------------------------|------------------------------------------------------|
| **Châssis**            | Structure supportant tous les éléments.             |
| **Moteurs + Hélices**  | Créent la portance. Paires CW/CCW pour le contrôle. |
| **ESCs**               | Contrôlent la vitesse des moteurs.                  |
| **Contrôleur de vol (FC)** | Cerveau du drone. Interprète les capteurs et commandes. |
| **Distribution d’Énergie (PDB)** | Alimente tous les composants.                     |
| **Batterie (LiPo)**    | Fournit une puissance à haute décharge.             |
| **Récepteur (RX)**     | Reçoit les commandes du pilote par radio.           |
| **GPS/Compas**         | Permet navigation, RTH, vol par points.             |
| **Caméra + VTX**       | Transmission vidéo pour FPV.                        |
| **Antenne**            | Essentielle pour la portée RC et FPV.               |

## III. 📶 Récepteurs Radio & Liens de Contrôle

| Protocole         | Caractéristiques                               | Remarques                           |
|-------------------|-------------------------------------------------|-------------------------------------|
| **ELRS**          | Latence ultra-faible, longue portée, open-source. | Préféré pour FPV, très personnalisable. |
| **FrSky (ACCST, ACCESS)** | Répandu, bon pour débutants.          | Moins de portée qu’ELRS.            |
| **TBS Crossfire** | Longue portée, stable, propriétaire.            | Utilisé pour FPV longue distance.   |
| **Contrôleur DJI**| Vidéo numérique + commande dans un seul lien.   | Pour l’écosystème DJI.              |

### Disposition du Contrôleur Radio Mode 2 :
- **Stick Gauche :** Gaz (↑↓), Lacet (←→)
- **Stick Droit :** Tangage (↑↓), Roulis (←→)

## IV. 🎥 Caméras et Systèmes Vidéo

| Type                      | Caractéristiques                    | Latence  | Usage                         |
|---------------------------|-------------------------------------|----------|-------------------------------|
| **FPV Analogique**        | Réponse rapide, faible latence.     | ~20 ms   | Course, freestyle.            |
| **FPV Numérique (DJI, Walksnail, HDZero)** | Vidéo HD, OSD, enregistrement. | 28–50 ms | FPV cinématique, setups haut de gamme. |

### Systèmes :
- **DJI Air Unit / O3 / Avata** : Qualité numérique maximale, propriétaire.
- **Walksnail Avatar** : Bonne alternative à DJI.
- **HDZero** : Numérique à faible latence, sur bande analogique.
- **OpenIPC** : Firmware open-source pour caméras IP (non FPV).

## V. 🔋 Batteries et Alimentation

### Spécifications Clés :
- **Cellules (S)** : 1S (3.7V) à 6S (22.2V) – plus de tension = plus de puissance.
- **Capacité (mAh)** : Durée de vol.
- **Indice C** : Taux de décharge. Plus élevé = plus de puissance instantanée.

### Sécurité & Charge :
- Toujours utiliser des **chargeurs équilibrés** (ISDT, ToolkitRC…).
- Ne jamais laisser en charge sans surveillance.
- Stocker à 3.8V/cellule (tension de stockage).
- Utiliser sacs ignifugés ou boîtes métalliques.
- Inspecter pour gonflement, dommages, surchauffe.

## VI. ✈️ Principes de Vol & Mixage Moteur

| Axe       | Mouvement        | Fonctionnement                                 |
|-----------|------------------|-----------------------------------------------|
| Gaz       | Haut/Bas         | Tous les moteurs augmentent/diminuent.        |
| Tangage   | Avant/Arrière    | Moteurs avant/arrière varient.                |
| Roulis    | Inclinaison G/D  | Moteurs latéraux varient.                     |
| Lacet     | Rotation CW/CCW  | Couple des moteurs CW contre CCW.             |

### Mixage Moteur (X-frame) :
| Moteur | Position        | Rotation | Rôle                          |
|--------|------------------|----------|-------------------------------|
| M1     | Avant Droit      | CW       | Roulis G / tangage bas        |
| M2     | Arrière Droit    | CCW      | Roulis G / tangage haut       |
| M3     | Arrière Gauche   | CW       | Roulis D / tangage haut       |
| M4     | Avant Gauche     | CCW      | Roulis D / tangage bas        |

## VII. 🧭 Capteurs et Systèmes de Navigation

| Capteur               | Utilisation                                      |
|-----------------------|--------------------------------------------------|
| **IMU (Gyro + Accéléro)** | Stabilisation, détection du mouvement.     |
| **Magnétomètre**      | Référence de direction.                         |
| **Baromètre**         | Maintien d’altitude.                            |
| **GPS**               | Position fixe, retour domicile, waypoints.     |
| **Optical Flow**      | Positionnement intérieur.                       |
| **ToF/Lidar/Ultrasons** | Détection d’altitude et d’obstacles.          |

## VIII. 📐 Rapport Portance/Poids

- **Portance ≥ 2× poids** pour bonne maniabilité.
- Exemple : Drone de 1.2 kg → portance ≥ 2.4 kg.
- Ajouter une marge pour vent, caméra, charge utile.

## IX. 🏗️ Étapes de Construction

1. Choisir le châssis, moteurs, FC, RX, GPS, caméra, VTX.
2. Assembler le châssis et fixer les moteurs.
3. Installer les ESCs et câbler.
4. Fixer le FC avec supports souples, câbler l’alimentation.
5. Connecter RX, VTX, caméra, GPS.
6. Installer connecteur batterie (XT60/XT90).
7. Sécuriser les antennes, protéger l’électronique.
8. Tester la continuité avant l’allumage.
9. Mettre les hélices **seulement à la fin**.

## X. 💻 Logiciels de Vol & Configuration

### 1. **Betaflight**
- Idéal pour course/freestyle FPV.
- Setup rapide, tuning PID, OSD, test moteurs.

### 2. **INAV**
- Pour drones GPS, retour, loiter, waypoints.
- Idéal longue portée ou ailes fixes.

### 3. **ArduPilot (ArduCopter)**
- Plateforme UAV complète, scripts, évitement obstacles.
- Utilisé dans la recherche, commerce, DIY avancé.

### Étapes de Configuration :
1. Flasher le firmware.
2. Calibrer les capteurs : gyro, compas, baro.
3. Attribuer les modes de vol (angle, horizon, acro, GPS).
4. Configurer armement, failsafe, retour à la maison.
5. Régler PID ou utiliser des presets.
6. Tester sans hélices, puis effectuer vol inaugural.

## XI. 📜 Réglementation des Drones (Style FAA)

| Règle                        | Résumé                                               |
|-----------------------------|-------------------------------------------------------|
| **Altitude Max (AGL)**      | 400 pieds (≈120 m) au-dessus du sol.                 |
| **Ligne de Vue Visuelle**   | Garder le contact visuel direct sans aide.           |
| **Vol au-dessus de personnes** | Interdit sauf drones certifiés Catégories 1–4.     |
| **Vol de nuit**             | Autorisé avec éclairage & dérogation.                |
| **Enregistrement du Drone** | Obligatoire si >250g.                                |
| **Identification à Distance** | Requise pour la plupart des drones aux USA.        |
| **Vol près d’aéroports**    | Autorisation LAANC requise en espace contrôlé.       |
| **Rapport d’Incidents**     | Si blessure ou dégâts >500$.                         |
| **Zones d’interdiction**    | Stades, parcs nationaux, infrastructures sensibles.  |
