FROM julia:1.3.1-stretch

RUN apt-get update
RUN apt-get install -y procps
RUN apt-get install -y python3 python3-pip telnet git wget nano net-tools zip unzip vim
RUN apt-get install -y apt-transport-https apt-utils apache2 libsasl2-dev python-dev libldap2-dev libssl-dev  python3-pyldap



# Install Jupyter
RUN pip3 install jupyter
RUN pip3 install ipywidgets
RUN jupyter nbextension enable --py widgetsnbextension

# Install JupyterLab
RUN pip3 install jupyterlab && jupyter serverextension enable --py jupyterlab

RUN julia -e "import Pkg;Pkg.add(\"DataFrames\")" && \
    julia -e "import Pkg;Pkg.add(\"CSV\")" && \
    julia -e "import Pkg;Pkg.add(\"XLSX\")" && \
    julia -e "import Pkg;Pkg.add(\"Mongoc\")" && \
    julia -e "import Pkg;Pkg.add(\"JSON\")" && \
    julia -e "import Pkg;Pkg.add(\"HTTP\")" && \
    julia -e "import Pkg;Pkg.add(\"JLD2\")" && \
    julia -e "import Pkg;Pkg.add(\"Plots\")" && \
    julia -e "import Pkg;Pkg.add(\"DataStructures\")" && \
    julia -e "import Pkg;Pkg.add(\"Formatting\")" && \
    julia -e "import Pkg;Pkg.add(\"Parsers\")" && \
    julia -e "import Pkg;Pkg.add(\"PyCall\")" && \
    julia -e "import Pkg;Pkg.add(\"ZipFile\")" && \
    julia -e "import Pkg;Pkg.add(\"XLSX\")" && \
    julia -e "import Pkg;Pkg.add(\"WebSockets\")"

RUN julia -e "import Pkg;Pkg.add(\"IJulia\")" && \
    julia -e "import Pkg;Pkg.build(\"IJulia\")"

ENV DIR /workspace
RUN mkdir $DIR
WORKDIR $DIR
CMD jupyter lab --ip=* --port=8888 --no-browser --allow-root --notebook-dir=$DIR
