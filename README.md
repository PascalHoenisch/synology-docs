# synology-docs
Setup docker compose projects

## Create folder

Create a folder under `docker/` e.g. `my-project`.

## Create Domain

Create domain at registrar and A record to your machine,
then under security -> certificate ->  create -> new certificate -> get cert from lets encrypt -> use fqdn as domain and select admin mail adr

## Configure domain 

Now we have to configure synology to use our new domain for the project. Go to System configuration -> security -> certificate -> settings -> select the new domain for the new domain, on standard configuration the standard domain will be choosen, but we do not want this. Then submit, the project should now be restarted.

## Create project

Under Container Manager go to project -> create -> set project name, path (/docker/my-project) and `docker-compose.yml create`. Then insert the complete configuration. Now tick `webportal via web station creation` leave port and project name and select HTTP. After clicking on complete a portal assistent window should open. Select Portaltype `name based`, for hostname insert the recent created domain name, for port select 80/443 and check HSTS.

Project should now be up and running.
