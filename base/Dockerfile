FROM julia:1.5.2-buster

RUN apt-get update
RUN apt-get install -y procps
RUN apt-get install -y python3 python3-pip telnet git wget nano net-tools zip unzip vim
RUN apt-get install -y apt-transport-https apt-utils apache2 libsasl2-dev python-dev libldap2-dev libssl-dev  python3-pyldap

# Julia Threads
ENV JULIA_NUM_THREADS 16

RUN julia -e "import Pkg;Pkg.add(\"DataFrames\")" && \
    julia -e "import Pkg;Pkg.add(\"CSV\")" && \
    julia -e "import Pkg;Pkg.add(\"XLSX\")" && \
    julia -e "import Pkg;Pkg.add(\"Mongoc\")" && \
    julia -e "import Pkg;Pkg.add(\"JSON\")" && \
    julia -e "import Pkg;Pkg.add(\"HTTP\")" && \
    julia -e "import Pkg;Pkg.add(\"Plots\")" && \
    julia -e "import Pkg;Pkg.add(\"DataStructures\")" && \
    julia -e "import Pkg;Pkg.add(\"Formatting\")" && \
    julia -e "import Pkg;Pkg.add(\"Parsers\")" && \
    julia -e "import Pkg;Pkg.add(\"PyCall\")" && \
    julia -e "import Pkg;Pkg.add(\"ZipFile\")" && \
    julia -e "import Pkg;Pkg.add(\"WebSockets\")"

CMD bash
