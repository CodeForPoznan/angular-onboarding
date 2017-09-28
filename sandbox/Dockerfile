FROM node:8.6

# Fix directory permissions for globally installed angular-cli
# See:
# https://docs.npmjs.com/getting-started/fixing-npm-permissions
# https://github.com/angular/angular-cli/issues/6800
RUN chown -R node $(npm config get prefix)/lib/node_modules
RUN chown -R node $(npm config get prefix)/bin
RUN chown -R node $(npm config get prefix)/share
USER node
RUN npm install -g @angular/cli

USER root
ADD . /angular-onboarding
WORKDIR /angular-onboarding
RUN npm install
