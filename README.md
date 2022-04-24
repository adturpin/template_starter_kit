# template starter kit
The goal of this repo is to make proposal for a setup for an application back + front an reverse proxy.

## source

### backend 
It's the sample dotnet core 5 web api

### frontend 
It's the sample Angular 13.3.0

### reverse proxy 
Nginx routing  
	
	/ 
	routing => frontend
	
	/api/
	routing => backend
	
The entrypoint is configurable with environement variable with the port of nginx. 

The file .env set by default the environement variable.

Doc: https://docs.docker.com/compose/env-file/


## infrastructure
### docker-compose

In directory `deploy/docker-compose` you can found 2 docker-compose files

- `docker-compose.build.yml` => configuration file to build the application stack
- `docker-compose.run.yml` => configuration file to run the application stack
- `build.ps1` => powershell for build all the stack image
- `run.ps1` => powershell for run all stack
- `.env` => The file set by default the environement variable, set of keys values.
 				
	



