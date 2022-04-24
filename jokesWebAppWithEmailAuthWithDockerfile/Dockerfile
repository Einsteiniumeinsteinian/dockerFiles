FROM	mcr.microsoft.com/dotnet/sdk:5.0 AS build-env

EXPOSE  80

EXPOSE	433
WORKDIR /app

RUN	git clone https://github.com/nelliejellie/jokesWebAppWithEmailAuth.git

WORKDIR	/app/jokesWebAppWithEmailAuth/JokesWebApp

RUN	dotnet restore

RUN	dotnet publish -c Realease -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/aspnet:5.0 

WORKDIR /app

COPY --from=build-env /app/jokesWebAppWithEmailAuth/JokesWebApp/out .

ENTRYPOINT ["dotnet", "JokesWebApp.dll"]

