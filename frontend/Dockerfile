FROM node:23-alpine AS build-stage

WORKDIR /frontend-app
COPY package.json ./
RUN npm install
COPY public public
COPY src src
RUN npm run build

FROM nginx:alpine
COPY --from=build-stage /frontend-app/build /usr/share/nginx/html
CMD [ "nginx", "-g", "daemon off;" ]


# 1. Navigate to the `frontend` directory:

#     ```sh
#     cd frontend
#     ```
 
#  2. Install the required dependencies:
 
#     ```sh
#     npm install
#     ```
 
#  3. Start the front-end development server:
 
#     ```sh
#     npm start
#     ```
 
#     The front-end server should now be running at `http://localhost:3000`.