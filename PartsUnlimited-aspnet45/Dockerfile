# Étape 1 : Build du projet .NET
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app

# Copier le code
COPY . .

# Restaurer et compiler
RUN dotnet restore
RUN dotnet publish -c Release -o /out

# Étape 2 : Runtime
FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app

COPY --from=build /out .

EXPOSE 8080

ENTRYPOINT ["dotnet", "PartsUnlimited.dll"]
