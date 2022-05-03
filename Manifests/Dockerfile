FROM mcr.microsoft.com/dotnet/core/sdk:5.0 AS build
WORKDIR /app

COPY HelloworldApp/*.csproj .
RUN dotnet restore

COPY HelloworldApp/ ..
RUN dotnet publish -c release -o /WebApp --no-restore

FROM mcr.microsoft.com/dotnet/core/aspnet:5.0
WORKDIR /WebApp
COPY --from=build /Webapp ./
ENTRYPOINT ["dotnet","Helloworld.dll"]