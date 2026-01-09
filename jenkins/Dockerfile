FROM jenkins/jenkins:alpine-jdk17

# Set environment variables to disable the setup wizard and specify the JCasC config file location
ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false"
ENV CASC_JENKINS_CONFIG="/var/jenkins_home/jenkins.yaml"

# Copy the plugins.txt file into the container's reference directory
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt

COPY jenkins.yaml /var/jenkins_home/jenkins.yaml

# Run the official script to install the plugins listed in plugins.txt
#RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
RUN jenkins-plugin-cli -f /usr/share/jenkins/ref/plugins.txt

# Copy the JCasC configuration file into the Jenkins home directory
COPY jenkins.yaml /var/jenkins_home/jenkins.yaml
