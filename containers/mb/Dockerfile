FROM nuwanbando/javabase

RUN mkdir wso2 

COPY packs/wso2mb-3.1.0.zip wso2/

RUN cd wso2/ && \
        unzip wso2mb-3.1.0.zip

CMD ["sh", "/wso2/wso2mb-3.1.0/bin/wso2server.sh"]

EXPOSE 9763
EXPOSE 9443
EXPOSE 5672
EXPOSE 1883
EXPOSE 8883
