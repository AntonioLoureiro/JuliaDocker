FROM mongo:3.2

RUN apt-get update
RUN apt-get install -y telnet git wget nano net-tools zip unzip vim ca-certificates curl

#ENV JULIA_PATH /usr/local/julia
#ENV PATH $JULIA_PATH/bin:$PATH
#ENV CURL_CA_BUNDLE /etc/ssl/certs/ca-certificates.crt

#ENV JULIA_VERSION 0.6.4
#ENV dirArch x86

#RUN curl -k -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/x64/0.6/julia-0.6.4-linux-x86_64.tar.gz"
#RUN mkdir "$JULIA_PATH"
#RUN tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1
#RUN rm julia.tar.gz;

#RUN julia -e  "Pkg.add(\"CSV\")"