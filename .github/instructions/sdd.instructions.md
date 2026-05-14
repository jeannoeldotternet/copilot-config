# Instructions Spécialisées SDD

## 🎯 Contexte d'Application
- **S'applique à** : `**/specs/**`, `**/specifications/**`, `**/*-api.md`, `**/*-spec.md`
- **Priorité** : Haute pour les fichiers de spécifications

## 📋 Méthodologie SDD (Spec-Driven Development)

### Flux de Développement
1. **Spécification First** : Écrire la spec Markdown avant le code
2. **Contrat Clair** : Interface + règles métier + exemples
3. **Génération IA** : Copilot génère le code C# conforme
4. **Tests d'Abord** : Valider la spec avant l'implémentation
5. **Sync Continu** : Tout changement part de la spec

### Structure des Spécifications

#### Format Obligatoire
```markdown
# Spécification : [Nom du Service]

## Contrat Technique
- **Namespace** : `Projet.Services.[Domaine]`
- **Interface** : `I[Service]Service`
- **Méthode principale** : `Task<[ReturnType]> [MethodName]Async([params])`

## Règles Métier
1. [Règle 1 claire et testable]
2. [Règle 2 claire et testable]
3. [Règle N...]

## Modèle de Données
- `[Entity]` : { `[Property]`: [Type], `[Property2]`: [Type] }

## Exemples d'Usage
- Scénario nominal
- Cas d'erreur
- Edge cases
```

## 🔧 Bonnes Pratiques SDD

### Rédaction des Spécifications
- **Langage métier** : Termes compréhensibles par le métier
- **Testable** : Chaque règle doit pouvoir être testée
- **Évolutive** : Facile à modifier sans casser le code
- **Minimaliste** : Seulement ce qui est nécessaire

### Génération de Code
- **Ancrage fort** : `@spec-file.md` dans les prompts
- **Validation** : Vérifier conformité avant commit
- **Refactoring** : Changer la spec, régénérer le code
- **Tests** : Couvrir tous les scénarios de la spec

### Maintenance
- **Source de vérité** : La spec Markdown est LA référence
- **Versionning** : Specs versionnées avec le code
- **Reviews** : Validation des specs avant implémentation
- **Documentation** : Specs = documentation vivante

## ✅ Patterns SDD Recommandés

### Service Météo
```markdown
# Spécification : Weather Service

## Contrat Technique
- Namespace : `WeatherApp.Core.Services`
- Interface : `IWeatherService`
- Méthode : `Task<WeatherReport> GetByCityAsync(string city)`

## Règles Métier
1. Si `city` est null/vide → `ArgumentException`
2. Température toujours en Celsius
3. Cache de 10 minutes obligatoire

## Modèle de Données
- `WeatherReport` : { `City`: string, `Celsius`: float, `Summary`: string }
```

### Repository Pattern
```markdown
# Spécification : User Repository

## Contrat Technique
- Interface : `IUserRepository`
- Méthode : `Task<User?> GetByIdAsync(Guid id)`

## Règles Métier
1. Retourner null si utilisateur inexistant
2. Ne pas lever d'exception pour utilisateur non trouvé
3. Inclure les rôles de l'utilisateur
```

## 🚫 Anti-Patterns SDD

- **Code First** : Coder avant d'écrire la spec
- **Specs Vagues** : Règles non testables
- **Duplication** : Même logique dans code et spec
- **Specs Mortes** : Specs non maintenues après génération
- **Over-Spec** : Trop de détails inutiles

## 🔗 Intégration avec Copilot

### Prompts Types
```
"Utilise @weather-api.md comme référence stricte.
Génère l'interface et l'implémentation WeatherService en C#.
Ne t'éloigne pas des règles métier définies."
```

### Validation Post-Génération
- [ ] Interface conforme au contrat
- [ ] Toutes les règles métier implémentées
- [ ] Tests couvrant les scénarios de la spec
- [ ] Gestion d'erreurs selon la spec</content>
<parameter name="filePath">c:\Users\jn\AppData\Roaming\Code\User\prompts\instructions\csharp.instructions.md