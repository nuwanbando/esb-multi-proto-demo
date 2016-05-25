FROM nuwanbando/javabase

RUN mkdir wso2 && \
	mkdir in && \
    mkdir out 

COPY packs/wso2esb-4.9.0.zip wso2/

RUN cd wso2/ && \
        unzip wso2esb-4.9.0.zip
        
COPY esb/artifacts/books.xml /in/
        
COPY esb/artifacts/mb-libs/* /wso2/wso2esb-4.9.0/repository/components/lib/

COPY esb/artifacts/jndi.properties /wso2/wso2esb-4.9.0/repository/conf/

COPY esb/artifacts/esb-proto-proj_1.0.0.car /wso2/wso2esb-4.9.0/repository/deployment/server/carbonapps/

CMD ["sh", "/wso2/wso2esb-4.9.0/bin/wso2server.sh"]

EXPOSE 9763
EXPOSE 9443
EXPOSE 8280
EXPOSE 8243