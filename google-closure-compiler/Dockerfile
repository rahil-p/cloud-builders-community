FROM openjdk:8

WORKDIR closure-compiler
ARG version="latest"
RUN \
  wget \
    --quiet \
    --output-document compiler.zip \
    "https://dl.google.com/closure-compiler/compiler-${version}.zip" && \
    ls && unzip compiler.zip -d .

RUN rm compiler.zip COPYING README.md
RUN mv closure-compiler-v20[0-9]*.jar closure-compiler.jar
RUN ls

ENTRYPOINT ["java","-jar","/closure-compiler/closure-compiler.jar"]
