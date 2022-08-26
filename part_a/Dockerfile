FROM jenkins/jenkins:lts

# this disable setup wizard and allow me to take the casc.yml as a conf file
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false

# coping casc.yml
COPY ./casc.yml /var/jenkins_home/casc.yml
ENV CASC_JENKINS_CONFIG /var/jenkins_home/casc.yml

# installing plugins.txt
COPY ./plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN jenkins-plugin-cli --clean-download-directory --list --view-security-warnings -f /usr/share/jenkins/ref/plugins.txt