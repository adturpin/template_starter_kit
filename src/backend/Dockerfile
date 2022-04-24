FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /src
COPY ["template.backend.app/template.backend.app.csproj", "template.backend.app/"]
RUN dotnet restore "template.backend.app/template.backend.app.csproj"
COPY . .
WORKDIR "/src/template.backend.app"
RUN dotnet build "template.backend.app.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "template.backend.app.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "template.backend.app.dll"]
