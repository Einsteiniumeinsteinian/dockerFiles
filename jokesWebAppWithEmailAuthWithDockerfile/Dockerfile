FROM	mcr.microsoft.com/dotnet/sdk:5.0 AS build-env

WORKDIR /app

RUN	git clone https://github.com/nelliejellie/jokesWebAppWithEmailAuth.git

WORKDIR	/app/jokesWebAppWithEmailAuth/JokesWebApp

RUN	dotnet restore

RUN	dotnet publish -c Realease -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/sdk:5.0 

WORKDIR /app

COPY --from=build-env /app/jokesWebAppWithEmailAuth/JokesWebApp/out .

#WORKDIR	/app/jokesWebAppWithEmailAuth/JokesWebApp

ENTRYPOINT ["dotnet", "JokesWebApp.dll"]

#WORKDIR /app

# Copy everything
#COPY . ./
# Restore as distinct layers
#RUN dotnet restore
# Build and publish a release
#RUN dotnet publish -c Release -o out

# Build runtime image
#FROM mcr.microsoft.com/dotnet/aspnet:6.0
#WORKDIR /app
#COPY --from=build-env /app/out .
#ENTRYPOINT ["dotnet", "DotNet.Docker.dll"]
