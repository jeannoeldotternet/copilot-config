# Instructions Spécialisées C#

## 🎯 Contexte d'Application
- **S'applique à** : `**/*.cs`, `**/*.csproj`, `**/*.sln`
- **Priorité** : Haute pour tous les fichiers C#

## 🏗️ Architecture & Patterns

### Clean Architecture
- Séparer clairement : Domain → Application → Infrastructure
- Interfaces dans les couches supérieures
- Dépendances pointent vers l'intérieur

### Patterns .NET
- **Repository Pattern** pour l'accès données
- **CQRS** pour séparation lecture/écriture
- **Mediator** (MediatR) pour les commandes/queries

## 📝 Conventions de Code

### Nommage
- **Classes** : PascalCase (ex: `WeatherService`)
- **Interfaces** : IPascalCase (ex: `IWeatherService`)
- **Méthodes** : PascalCase (ex: `GetWeatherAsync`)
- **Propriétés** : PascalCase (ex: `CurrentTemperature`)
- **Variables privées** : camelCase (ex: `_weatherApiKey`)

### Async/Await
- Toutes les méthodes I/O : `async Task<T>`
- Pas de `.Result` ou `.Wait()` (deadlock)
- `ConfigureAwait(false)` pour les libs

## 🔧 Bonnes Pratiques

### Gestion des Erreurs
- **Exceptions métier** : classes dédiées héritant de `Exception`
- **Validation** : FluentValidation ou DataAnnotations
- **Logging** : Serilog ou Microsoft.Extensions.Logging

### Tests
- **xUnit** ou **NUnit** pour les tests unitaires
- **Moq** pour les mocks
- **FluentAssertions** pour les assertions lisibles

### Performance
- **LINQ** pour les requêtes (optimisé par le compilateur)
- **Span<T>** pour les manipulations de mémoire
- **Records** pour les DTO immuables

## ✅ Code Idiomatique C#

### Collections
```csharp
// ✅ LINQ fluide
var activeUsers = users.Where(u => u.IsActive)
                      .OrderBy(u => u.Name)
                      .ToList();

// ❌ Évite les boucles manuelles
```

### Pattern Matching
```csharp
// ✅ Switch expressions modernes
var result = status switch {
    Status.Active => "Actif",
    Status.Inactive => "Inactif",
    _ => "Inconnu"
};
```

### Null Safety
```csharp
// ✅ Null-conditional et coalescing
var name = user?.Name ?? "Anonyme";

// ✅ Records pour DTO
public record WeatherReport(string City, double Celsius, string Summary);
```

## 🚫 Anti-Patterns à Éviter

- **Singletons** (difficile à tester)
- **Static classes** pour la logique métier
- **God classes** (trop de responsabilités)
- **Primitive obsession** (utiliser des Value Objects)
- **Magic strings/numbers** (constantes nommées)