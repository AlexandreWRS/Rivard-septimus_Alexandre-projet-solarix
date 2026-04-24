# Analyse de la maquette

## Composants identifiés :

### DEKSTOP 

Sidebar à gauche 

1. Avatar utilisateur

2. Nom + niveau

3- Menu :

- Profil

- Quêtes

- Inventaire

- Guilde

- Contenu principal à droite



### MOBILE

Header en haut

Contenu en colonne

Navigation en bas


## Carte de quête 

### Chaque carte contient :

Image

Badge (EN COURS / TERMINÉ)

Titre

Description

Récompense (XP + objet)

> Ajout de: voire toutes les quêtes (en haut à droite des cartes  quetes)

## Nomenclature CSS prévue


 .layout
 
 .layout__sidebar 
 
 .layout__main
  


.sidebar

.sidebar__profile

.sidebar__menu

.sidebar__item


.header

.header__title

.header__icons


.profile-card

.profile-card__image

.profile-card__name

.profile-card__level

.profile-card__progress

.profile-card__bar


.quests

.quests__header

.quests__list

.quest-card

.quest-card__image

.quest-card__badge

.quest-card__title


.quest-card__description

.quest-card__reward

.quest-card__badge--active

.quest-card__badge--completed





.nav-mobile

.nav-mobile__item

## Découpage en tâches (logique pour TON projet)

- Créer structure HTML globale
  
- Faire le layout (sidebar + main)
  
- Créer le header
  
- Créer la carte profil
  
- Créer UNE quest-card (modèle)
  
- Dupliquer pour les autres
  
- Ajouter la section quêtes
  
- Créer la navigation mobile
  
- Ajouter la zone stats
  
- Styliser (couleurs, spacing)
  
Responsive (mobile ↔ desktop)

## Stratégie responsive

Je commence par concevoir l’interface pour les écrans (desktop), puis j’adapte l’interface pour les écrans plus petits à l’aide de media queries.

 ### comment je vais faire ?
 
  #### Layout global
   
Desktop : layout en grille avec sidebar + contenu principal
Mobile : passage en colonne, suppression de la sidebar

 #### Sidebar
Desktop : visible à gauche
Mobile : cachée

-  Remplacée par une navigation en bas de l’écran

  ### Exemple

  .layout  {
  display: grid;
  grid-template-columns: 250px 1fr;
}



/* Sidebar visible */

.sidebar {
  display: block;
}



/* Navigation mobile cachée */

.nav-mobile {
  display: none;
}


@media (max-width: 768px) {

  /* Layout devient en colonne */
  
  .layout {
    display: block;
  }
  

  /* Sidebar disparaît */
  
  .sidebar {
    display: none;
  }
  

  /* Navigation mobile apparaît */
  
  .nav-mobile {
    display: flex;
    position: fixed;
    bottom: 0;
    width: 100%;
  }
}

J’utilise une media query avec max-width: 768px pour adapter le layout en mobile. La sidebar est masquée et remplacée par une navigation fixe en bas de l’écran, tandis que le layout passe d’une grille à une disposition en colonne.

## Mise en page

### Mobile :

Les statistiques seront affichées en colonne
Chaque statistique sera dans une carte (card) avec :
une valeur mise en évidence
un label en dessous

### Desktop :

Les statistiques seront affichées en grille (2x2 ou 4 colonnes)
Alignées avec le reste du contenu (comme les quest cards)
 Cohérence avec l’interface

Pour rester cohérent avec le design existant :

- Utilisation du même style que les cartes de quêtes
- coins arrondis
- ombres légères
- couleurs douces
  
- Hiérarchie visuelle :

1 valeur en gros (stats__value)
  
2 texte plus petit pour le label

3 Espacement similaire aux autres sections
