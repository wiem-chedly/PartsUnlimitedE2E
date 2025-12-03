# Image de base pour ASP.NET 4.5
FROM mcr.microsoft.com/dotnet/framework/aspnet:4.8-windowsservercore-ltsc2019

# Copier les fichiers de ton projet buildés
WORKDIR /inetpub/wwwroot
COPY ./PartsUnlimited/ ./

# Exposer le port IIS
EXPOSE 80
