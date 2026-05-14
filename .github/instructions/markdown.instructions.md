# Instructions Spécialisées Markdown

## 🎯 Contexte d'Application
- **S'applique à** : `**/*.md`
- **Priorité** : Moyenne pour tous les fichiers Markdown

## 📋 Structure Obligatoire des Documents

### Format Général
- **Documents synthétiques** : Concis, structuré, sans verbosité inutile
- **Navigation claire** : Liens internes cohérents
- **Hiérarchie logique** : Titres H1 → H2 → H3 (pas de sauts)

### Navigation Requise

#### 1. Sommaire en Tête
```markdown
# Titre du Document

## Sommaire
- [Chapitre 1 : Introduction](#chapitre-1--introduction)
- [Chapitre 2 : Concepts Clés](#chapitre-2--concepts-cles)
- [Chapitre 3 : Mise en Pratique](#chapitre-3--mise-en-pratique)
- [Chapitre 4 : Conclusion](#chapitre-4--conclusion)
```

#### 2. Liens de Navigation par Chapitre
```markdown
## Chapitre 1 : Introduction

[⬆️ Retour au sommaire](#sommaire)

*Contenu du chapitre...*

[⬆️ Retour au sommaire](#sommaire) | [Chapitre suivant : Concepts Clés](#chapitre-2--concepts-cles)
```

#### 3. Liens de Pied de Chapitre
```markdown
---

[⬆️ Retour au sommaire](#sommaire) | [Chapitre suivant](#chapitre-2--concepts-cles)
```

## ✍️ Conventions de Rédaction

### Titres et Ancres
- **Titres descriptifs** : Pascal Case avec émojis pertinents
- **Ancres HTML** : Minuscules, tirets au lieu d'espaces
- **Numérotation** : Cohérente (Chapitre 1, 2, 3...)

### Liens Internes
- **Syntaxe** : `[Texte](#ancre-minuscule-tirets)`
- **Cohérence** : Même ancre dans sommaire et titre
- **Navigation** : Toujours des liens retour au sommaire

### Mise en Forme
- **Code** : `inline` pour éléments techniques
- **Blocs** : ```language pour exemples de code
- **Listes** : - pour puces, 1. 2. 3. pour numérotation
- **Tableaux** : Pour comparaisons ou données structurées

## 📖 Patterns de Structure

### Document Technique
```markdown
# Titre : Description

## Sommaire
- [Section 1](#section-1)
- [Section 2](#section-2)

## Section 1
[⬆️ Retour au sommaire](#sommaire)

Contenu...

[⬆️ Retour au sommaire](#sommaire) | [Section suivante](#section-2)

## Section 2
[⬆️ Retour au sommaire](#sommaire)

Contenu...

[⬆️ Retour au sommaire](#sommaire)
```

### Document de Notes
```markdown
# Notes : Sujet

## Sommaire
- [1. Définition](#1-definition)
- [2. Exemples](#2-exemples)
- [3. Applications](#3-applications)

## 1. Définition
[⬆️ Retour au sommaire](#sommaire)

*Contenu concis...*

[⬆️ Retour au sommaire](#sommaire) | [2. Exemples](#2-exemples)
```

## 🎨 Émojis et Symboles

### Navigation
- ⬆️ : Retour au sommaire
- ➡️ : Chapitre suivant
- ⬅️ : Chapitre précédent
- 📋 : Sommaire
- 🔗 : Liens importants

### Contenu
- ✅ : Recommandations
- ❌ : À éviter
- 💡 : Conseils
- ⚠️ : Attention
- 📝 : Notes

## 📏 Règles de Longueur

### Chapitres
- **Maximum** : 500 mots par chapitre
- **Idéal** : 200-300 mots
- **Minimum** : 50 mots (chapitres trop courts = fusionner)

### Document Total
- **Synthétique** : < 2000 mots
- **Complet** : < 5000 mots
- **Référence** : Selon complexité (pas de limite)

## 🔍 Qualité et Cohérence

### Vérifications Automatiques
- [ ] Tous les liens internes fonctionnels
- [ ] Sommaire complet et à jour
- [ ] Navigation bidirectionnelle
- [ ] Ancres cohérentes avec titres

### Relectures
- [ ] Structure logique
- [ ] Navigation fluide
- [ ] Contenu synthétique
- [ ] Liens fonctionnels

## 🚫 Anti-Patterns à Éviter

- **Documents linéaires** sans sommaire
- **Liens cassés** ou ancres incorrectes
- **Navigation manquante** en tête/pied de chapitre
- **Titres sans ancres** appropriées
- **Contenu verbeux** (privilégier concision)
- **Sauts de hiérarchie** (H1 → H3 sans H2)