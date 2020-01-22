FROM rubensa/ubuntu-tini-dev

ARG NODE_VERSION=v12.13.1

# Allow vscode-server cache
RUN mkdir -p /home/${USER_NAME}/.vscode-server

# Create node environment
RUN /bin/bash -l -c ". /opt/nvm/nvm.sh; nvm install ${NODE_VERSION}"

# Configure local node modules
RUN printf "\nexport PATH=\"\$PWD/node_modules/.bin:\$PATH\"\n" >> /home/${USER_NAME}/.bashrc

# Keep container running (for use in VSCode)
CMD [ "tail", "-f", "/dev/null" ]
