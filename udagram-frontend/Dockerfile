# ## Construire
# FROM beevelop/ionic:latest AS ionic
# ## Créer le répertoire de l'application
# WORKDIR /usr/src/app
# # Installer les dépendances de l'application
# # Un joker est utilisé pour s'assurer que package.json ET package-lock.json sont copiés.
# COPY package*.json ./
# RUN npm ci
# # Regroupement des sources de l'application
# COPY . .
# RUN ionic build
# ## Exécuter
# FROM nginx:alpine
# # COPY www /usr/share/nginx/html
# COPY --from=ionic /usr/src/app/www /usr/share/nginx/html

# 

FROM beevelop/ionic:latest AS ionic

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm ci

COPY . .
RUN ionic build

FROM nginx:alpine

COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html