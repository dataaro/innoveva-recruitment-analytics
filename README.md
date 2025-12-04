# innoveva-recruitment-analytics
Projet de suivi de la performance de l'activité de recrutement de Innoveva : Modélisation, DAX, Dashboard et Rapports BI
Le management souhaite optimiser le processus de recrutement et réaliser des gains sur ordre de la direction générale.

Ce repository présente les analyses du processus de recrutement d’Innoveva
  Le travail se base strictement sur :
Dim_Candidat
Dim_Poste
Dim_Consultant
Dim_Client
Dim_Etape
Dim_Motif
F_Recrutement

## Objectifs

- Comprendre la performance du processus recrutement
- Analyser la vitesse et la qualité du traitement des candidatures
- Mesurer les performances des consultants
- Identifier les causes principales de perte de candidats
- Calculer les temps de traitement par étape

## Business Questions couvertes

### 1. Performance du Funnel
Où perd-on le plus de candidats ?
Quelle étape est la plus lente ?
Quels postes / clients génèrent le plus de pertes ?

### 2. Time-to-Hire
Durée moyenne entre candidature et placement
Durée par consultant
Durée par poste

### 3. Performance Consultant
Nombre de candidatures traitées
Placements finalisés
Abandons
Effort vs résultat

### 4. Motifs de perte
Quels motifs dominent ?
Par consultant ?
Par type de poste ?

## Tables utilisées

### Tables de faits
#### F_Recrutement
Chaque ligne représente une étape du processus pour un candidat. Champs clés :
- CandidatID
- ConsultantID
- PosteID
- ClientID
- EtapeID
- MotifID
- DateEtape
- Statut (terminé, en cours)

### Dimensions
#### Dim_Candidat
Infos générales (nom, genre, expérience, etc.)

#### Dim_Poste
Poste sur lequel le candidat postule.

#### Dim_Client
Entreprise cliente liée au recrutement.

#### Dim_Consultant
Consultant RH en charge du dossier.

#### Dim_Etape
Étapes officielles du recrutement :
- Sourcing
- Screening
- Entretien RH
- Entretien Client
- Shortlist
- Placement
- Lost

#### Dim_Motif
Motifs de perte :
Non retenu
Client refus
Salaire
Désistement
Incomplet

#### Dim_Date
Générée automatiquement pour les analyses temporelles.



Dim_Candidat     ┐
Dim_Consultant   │
Dim_Poste        │
Dim_Client       │
Dim_Motif        ├── F_Recrutement ─── Dim_Date
Dim_Etape        │
                 ┘


## KPI DAX inclus

Dans /dax/.

### Funnel
+ Total Candidats
+ Candidats par Étape
+ % Conversion Étape → Étape
+ % Abandon

### Temps
+ Time-to-Hire
+ Temps moyen par Étape
+ Temps moyen par Consultant
+ Lead Time global

### Motifs
+ Répartition des motifs de perte
+ Motifs par consultant
+ Motifs par poste

### Consultants
+ Productivité
+ Taux de placement
+ Perte vs réussite

## Dashboards inclus

Vue globale Recrutement

Funnel complet multi-étapes

Analyse durée recrutement

Analyse des motifs de perte

Performances consultant

Analyse par poste

Analyse par client

## Instructions

Cloner le repo

Charger tous les CSV du dossier /data

Charger les mesures DAX du dossier /dax

Ouvrir le fichier PBIX

Explorer les visualisations

## Données

Toutes les données sont intégralement fictives.
