# Strapi azure docker image
## Ready to use strapi docker image for Azure cloud integration

**Full integration in Azure with Blob storage, File share and Azure front door CDN**

This image was configured to use azure storage as media storage
Supported databases: sqlite (default/standalone), mysql, postgre

This image and his dependencies was intregrated successively in Azure cloud hosting with following resources:

- Strapi image could be stored in a Azure container registry
- Strapi instance is hosted in a Azure Container Instance
- Strapi database is hosted in managed Azure MySQL flexible server
- Strapi app directory is mounted to Azure Storage File Shares
- Strapi medias are hosted in Azure Blob Storage behind with a Azure Front door CDN

To configure database and storage informations, you just need to provide .env file in docker compose running context

By default, this image instance start in production mode (yarn start)
"dev" prefix on docker image name indicates that instance is in developer mode (yarn develop)

 
