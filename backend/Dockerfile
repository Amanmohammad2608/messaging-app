FROM node:16 
RUN mkdir /backend 
WORKDIR /backend 
COPY . /backend 
RUN npm install 
RUN npx prisma generate 
RUN npx prisma db push 
RUN npm run build 
RUN mkdir -p build/src && cp src/openapi.yaml build/src/
EXPOSE 8080 
CMD ["node", "build/src/index.js"] 