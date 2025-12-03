# 1. Image Windows Server + IIS + .NET Framework 4.8
# (Compatible ASP.NET 4.5)
FROM mcr.microsoft.com/dotnet/framework/aspnet:4.8

# 2. Définir le dossier par défaut d’IIS
WORKDIR /inetpub/wwwroot

# 3. Copier ton site ASP.NET dans IIS
COPY . .

# (optionnel) 4. Définir le port si besoin
EXPOSE 80
