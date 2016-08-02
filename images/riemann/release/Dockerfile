FROM colstrom/java

RUN package install bash

ENV PACKAGE_ROOT=/package
ENV NAMESPACE=host/github.com/riemann

ADD archive/riemann-*.tar.bz2 $PACKAGE_ROOT/$NAMESPACE

COPY meta /meta

RUN env PATH=/meta/command:$PATH build

ENV PATH=$PATH:$PACKAGE_ROOT/$NAMESPACE/riemann/bin

ENTRYPOINT ["riemann"]
