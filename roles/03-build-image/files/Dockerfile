FROM jatayu99/my-tomcat:latest
ADD prometheus-jmx-config.yml /prometheus-jmx-config.yml
ADD jmx_prometheus_javaagent-0.13.0.jar /jmx_prometheus_javaagent-0.13.0.jar
COPY ConferenceRoomCapstoneB35.war /usr/local/tomcat/webapps
ENV CATALINA_OPTS="-Xms64m -Xmx128m -javaagent:/jmx_prometheus_javaagent-0.13.0.jar=6060:/prometheus-jmx-config.yml"
#ENV JAVA_OPTS="$JAVA_OPTS -javaagent:/jmx_prometheus_javaagent-0.13.0.jar=9830:/prometheus-jmx-config.yml"
#ENV CATALINA_OPTS=-Dcom.sun.management.jmxremote.port=9830 -Dcom.sun.management.jmxremote.rmi.port=9830 -Dcom.sun.management.jmxremote.ssl=false -Dcom.sun.management.jmxremote.authenticate=false
EXPOSE 6060 8080
CMD ["/usr/local/tomcat/bin/catalina.sh", "run"]
