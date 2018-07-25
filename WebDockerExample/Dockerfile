FROM microsoft/dotnet:2.1-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /src
COPY WebDockerExample/WebDockerExample.csproj WebDockerExample/
RUN dotnet restore WebDockerExample/WebDockerExample.csproj
COPY . .
WORKDIR /src/WebDockerExample
RUN dotnet build WebDockerExample.csproj -c Release -o /app

FROM build AS publish
RUN dotnet publish WebDockerExample.csproj -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebDockerExample.dll"]
