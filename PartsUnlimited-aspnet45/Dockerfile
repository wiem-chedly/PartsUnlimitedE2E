FROM mcr.microsoft.com/dotnet/framework/aspnet:4.8
WORKDIR /app
COPY . .
RUN msbuild PartsUnlimited.sln /p:Configuration=Release
CMD ["PartsUnlimited.exe"]
