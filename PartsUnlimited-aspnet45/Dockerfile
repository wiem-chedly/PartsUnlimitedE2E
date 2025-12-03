# Étape 1 : Base Linux .NET 7
FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS base
WORKDIR /app

# Copier tous les fichiers du projet
COPY . .

# Construire le projet
RUN dotnet build

# Commande pour lancer l'application
CMD ["dotnet", "run"]
