FROM jenkins/jenkins:latest
LABEL org.opencontainers.image.authors="danilkaspirin@gmail.com"

# Пропускаем мастер установки Jenkins
ENV JAVA_OPTS=-Djenkins.install.runSetupWizard=false

# Устанавливаем необходимые плагины(закоментировать ненужные)
COPY --chown=jenkins:jenkins plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN jenkins-plugin-cli -f /usr/share/jenkins/ref/plugins.txt

# Jenkins конфигурация
ENV CASC_JENKINS_CONFIG=/var/jenkins_home/jenkins.yaml
COPY jenkins.yaml /var/jenkins_home/jenkins.yaml

EXPOSE 8080
EXPOSE 50000
