 ## Wildfly Docker Image ##
 
This is a Docker Image containing:
- OpenJDK 8
- Wildfly

The wildfly-version is matched to the tag-version

The management Interface is exposed on port 9990 on the container.
The Server is running on Port 80 on the container.

If you need to add a management user, just extends this image like this:

FROM jboss/wildfly
RUN /opt/jboss/wildfly/bin/add-user.sh admin Admin#70365 --silent
CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0"]