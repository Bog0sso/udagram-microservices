FROM node:13
# Créer le répertoire de l'application
WORKDIR /usr/src/app
# Installer les dépendances de l'application
# Un joker est utilisé pour s'assurer que le paquet.json ET le paquet-lock.json sont copiés lorsqu'ils sont disponibles (npm@5+)
COPY package*.json ./
# 
#Install aws cli
# RUN apt-get update && apt-get install -y python python-dev python-pip python-setuptools \
#     && pip install awscli && apt-get clean

# # args
# ARG AWS_KEY=AKIAWCEYEN3WOUK3LI6E
# ARG AWS_SECRET=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
# ARG AWS_REGION=us-east-2
# RUN aws configure set aws_access_key_id $AWS_KEY
# RUN aws configure set aws_secret_access_key $AWS_SECRET
# RUN aws configure set region $AWS_REGION
# Regroupement des sources de l'application
# 
RUN npm ci
# Debugging
RUN npm --version 
# Regroupement des sources de l'application
COPY . .
EXPOSE 8080
CMD [ "npm", "run", "prod" ]