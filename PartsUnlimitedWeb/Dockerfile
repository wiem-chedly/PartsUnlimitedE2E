# 1. Image officielle .NET 6 Runtime pour ASP.NET Core
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80

# 2. Image SDK pour build
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
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
