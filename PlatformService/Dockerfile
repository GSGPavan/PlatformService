FROM mcr.microsoft.com/dotnet/sdk:8.0 as build-env
WORKDIR /app
COPY . ./
RUN dotnet restore
RUN dotnet publish -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /App
COPY --from=build-env /app/out .
ENTRYPOINT ["dotnet", "PlatformService.dll"]