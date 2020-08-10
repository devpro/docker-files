# ASP.NET Core Web application sample

## How to build & run with Docker


```bash
# build a new image (from solution root folder)
docker build . -t devpro-samples/aspnetcore-web -f src/AspNetCoreWebApp/Dockerfile --no-cache

# check image in local repository
docker images

# run a container on the new image
docker run -it --rm -p 8080:80 --name aspnetcorewebsample devpro-samples/aspnetcore-web

# open http://localhost:8080/ in a browser

# generate local certificate (see https://docs.microsoft.com/en-us/aspnet/core/security/docker-https?view=aspnetcore-3.1)
dotnet dev-certs https --clean
dotnet dev-certs https -ep %USERPROFILE%\.aspnet\https\aspnetapp.pfx -p <password>
dotnet dev-certs https --trust

# run a container with HTTPS
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/aspnetapp.pfx -v %USERPROFILE%\.aspnet\https:/https/ --name aspnetcorewebsample devpro-samples/aspnetcore-web

# open http://localhost:8000/ in a browser (you should be redirected to https://localhost:8001/)

# if there is an issue (direct crash), replace the ENTRYPOINT line by CMD "/bin/bash" in Dockerfile, build the image and run a new container
docker run -i -t -p 8080:80 devpro-samples/aspnetcore-web

# clean up
docker system prune -f
```
