FROM davidcaste/alpine-tomcat:jdk8tomcat8

ADD shipment /usr/local/shipment

ENV SOISRV_HOST=redmond.lhs-systems.com \
    SOISRV_PORT=20100 \
    BSCS_ROOT=/usr/local/shipment
ENV BSCS_JAR=$BSCS_ROOT/lib/jar \
    BSCS_SCRIPTS=$BSCS_ROOT/scripts \
    BSCS_RESOURCE=$BSCS_ROOT/resource\
    BSCS_3PP_JAR=$BSCS_ROOT/3pp/jar \
    BSCS_LOG=$BSCS_ROOT/log

RUN cd /usr/local/shipment && \
    ./environment.sh && \
    ./scripts/deploy_custcare.sh cu

CMD ["/opt/tomcat/bin/catalina.sh", "run"]
