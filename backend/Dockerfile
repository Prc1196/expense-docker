#FROM node:20
# Intermediate container -1 (IC-1)
FROM node:20.18.3-alpine3.21
# On top of IC-1 instruction-2 is executed, and save this layer 2nd image. IC-1 removed
RUN addgroup -S expense  && adduser -S expense -G expense && \ 
#Create IC-2, on top of IC-2 instruction-3 is executed and save this as layer3 image.IC-2 removed
    mkdir /opt/backend && \
    chown -R expense:expense /opt/backend
WORKDIR /opt/backend
ENV DB_HOST="mysql"
#ENV DB_HOST="localhost"
USER expense
COPY package.json ./
COPY *.js ./
RUN npm install
CMD ["node", "index.js"]
