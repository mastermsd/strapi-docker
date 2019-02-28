FROM node:11.1.0-alpine

COPY ./ ./

USER root

RUN npm install

RUN npm --prefix ./admin install ./admin

RUN npm --prefix ./plugins/content-manager/ install ./plugins/content-manager/
RUN npm --prefix ./plugins/content-type-builder/ install ./plugins/content-type-builder/
RUN npm --prefix ./plugins/email/ install ./plugins/email/
RUN npm --prefix ./plugins/settings-manager/ install ./plugins/settings-manager/
RUN npm --prefix ./plugins/upload/ install ./plugins/upload/
RUN npm --prefix ./plugins/users-permissions/ install ./plugins/users-permissions/

RUN chmod -R 777 ./admin/config
RUN chmod -R 777 ./admin/admin/src/config
RUN chmod -R 777 ./admin/admin/build

RUN chmod -R 777 ./plugins/content-manager/config
RUN chmod -R 777 ./plugins/content-type-builder/config
RUN chmod -R 777 ./plugins/email/config
RUN chmod -R 777 ./plugins/settings-manager/config
RUN chmod -R 777 ./plugins/upload/config
RUN chmod -R 777 ./plugins/users-permissions/config

USER node

EXPOSE 1337

CMD ["npm", "start"]
