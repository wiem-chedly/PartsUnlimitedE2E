# 1. Image officielle .NET 6 Runtime pour ASP.NET Core
FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS base
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /app
EXPOSE 80

WORKDIR /src

# Copier le csproj et restaurer les dépendances
COPY PartsUnlimitedWeb/PartsUnlimitedWeb.csproj ./
RUN dotnet restore PartsUnlimitedWeb.csproj

# Copier tout le projet et build
COPY PartsUnlimitedWeb/. ./
RUN dotnet publish PartsUnlimitedWeb.csproj -c Release -o /app/published

# 3. Construire l'image finale
FROM base AS final
WORKDIR /app
COPY --from=build /app/published .
ENTRYPOINT ["dotnet", "PartsUnlimitedWeb.dll"]
