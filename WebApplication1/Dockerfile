#FROM microsoft/dotnet:sdk AS build-env
#WORKDIR /app
#
#
#COPY *.csproj ./
#RUN dotnet restore
#
#
#COPY . ./
#RUN dotnet publish -c Release -o out
#
#FROM microsoft/dotnet:runtime
#WORKDIR /app
#
#
#COPY --from=build-env /app/out ./
#ENTRYPOINT ["dotnet", "RakshithACSDemo.dll"]
#
##FROM microsoft/dotnet:sdk AS build-env
##WORKDIR /app
##
### copy csproj and restore as distinct layers
##COPY . ./
##RUN dotnet restore
##
### copy everything else and build
##COPY . ./
##RUN dotnet publish -c Release -o out
##
### build runtime image
##FROM microsoft/dotnet:runtime
##WORKDIR /app
##COPY --from=build-env /app/out ./
##ENTRYPOINT ["dotnet", "RakshithACSDemo.dll"]
##



FROM microsoft/dotnet:latest
COPY . /api
WORKDIR /api
 
RUN ["dotnet", "restore"]
RUN ["dotnet", "build"]
 
ENV ASPNETCORE_URLS http://*:5000
EXPOSE 5000/tcp

ENTRYPOINT ["dotnet", "run"]
 