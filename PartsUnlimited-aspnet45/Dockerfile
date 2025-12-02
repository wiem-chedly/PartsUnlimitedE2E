# ===========================================================
# Dockerfile pour PartsUnlimited
# ===========================================================

# Étape 1 : Build de l'application
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY . .
RUN dotnet restore PartsUnlimited.sln
RUN dotnet publish PartsUnlimited.sln -c Release -o /app/publish

# Étape 2 : Image finale (runtime)
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS final
WORKDIR /app
COPY --from=build /app/publish .
ENTRYPOINT ["dotnet", "PartsUnlimitedWeb.dll"]
