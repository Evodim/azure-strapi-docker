ARG NODE_VERSION="14.20.0"
FROM node:${NODE_VERSION}
#supported databases : 'sqlite' , 'mysql' or 'postgres'
ARG DATABASE_CLIENT="sqlite"

ENV DBCLIENT=${DBCLIENT}

RUN apt-get -y update && apt -y install nano
WORKDIR /srv/app
VOLUME /srv/app 
RUN echo $NODE_VERSION
RUN echo $DATABASE_CLIENT

RUN  yarn create strapi-app . \
    --dbclient=$DATABASE_CLIENT \
    --dbhost=$DATABASE_HOST \
    --dbport=$DATABASE_PORT \
    --dbname=$DATABASE_NAME \
    --dbusername=$DATABASE_USERNAME \
    --dbpassword=$DATABASE_PASSWORD \
    --dbssl=$DATABASE_SSL \  
    --no-run

RUN yarn add mysql 
RUN yarn add pg
RUN yarn add strapi-provider-upload-azure-storage  
RUN yarn add @strapi/plugin-documentation
RUN yarn add @strapi/database 
COPY config config
COPY src src
RUN yarn build  
EXPOSE 1337   
ENTRYPOINT ["yarn"]
CMD ["start"]
