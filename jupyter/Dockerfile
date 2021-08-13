FROM jupyter/datascience-notebook:lab-3.0.12

USER root

ENV NB_UID=500 \
	NB_GID=500 \
	GRANT_SUDO=yes \
	JUPYTER_ENABLE_LAB=yes \
	RESTARTABLE=yes 
    
RUN sudo apt-get update -y && sudo apt-get install -y jq ripgrep pandoc mongodb-clients && \
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "/tmp/awscliv2.zip" && unzip -q /tmp/awscliv2.zip -d /tmp/ && sudo /tmp/aws/install && \
    wget -qO- "https://github.com/phiresky/ripgrep-all/releases/download/v0.9.6/ripgrep_all-v0.9.6-x86_64-unknown-linux-musl.tar.gz" | sudo tar -xvz -C /usr/local/bin/ --strip-components 1 --no-anchored --wildcards 'rga*' && \
    wget -qO- https://get.docker.com/ | sh && \
    
    pip install LAMP-core && \
    pip install fuzzywuzzy && \
    pip install python-levenshtein && \
    pip install pytz && \
    pip install tzwhere && \
    pip install geopy && \
    pip install similaritymeasures && \
    pip install fastdtw && \
    pip install altair && \
    pip install compress_pickle && \
    pip install pymongo && \
    pip install bash_kernel && python3 -m bash_kernel.install && \
    npm install -g tslab && tslab install && \

    pip install jupyterlab-lsp && \
    pip install 'python-language-server[all]' && \

    npm i -g bash-language-server && \
    npm i -g vscode-css-languageserver-bin && \
    npm i -g dockerfile-language-server-nodejs && \
    npm i -g vscode-html-languageserver-bin && \
    npm i -g javascript-typescript-langserver && \
    npm i -g vscode-json-languageserver-bin && \
    npm i -g yaml-language-server && \
    npm i -g unified-language-server && \

    pip install jupyterlab-git==0.30.0b3 && \
    pip install lckr-jupyterlab-variableinspector && \
    pip install jupyterlab-tabular-data-editor && \
    pip install jupyterlab-code-snippets && \
    pip install ipylab && \
    pip install jupytext && \

    jupyter labextension install jupyterlab_onedarkpro
    
WORKDIR /home

ENTRYPOINT ["start-notebook.sh"]
