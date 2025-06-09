# SonarQube Demo

## Setup SonarQube Community Server
```
docker run -d --name sonarqube \
  -p 9000:9000 \
  sonarqube:community
```

Access the SonarQube Dashboard
<pre>
http://localhost:9000  
</pre>

Login Credentials
<pre>
Username: admin
Password: admin  
</pre>

## Install SonarQube CLI tool in Ubuntu
```
sudo apt install unzip
wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-5.0.1.3006-linux.zip
unzip sonar-scanner-cli-*.zip
sudo mv sonar-scanner-*/ /opt/sonar-scanner
export PATH=$PATH:/opt/sonar-scanner/bin
source ~/.bashrc
```

## Create a sample project sonar-project.properties
<pre>
sonar.projectKey=demo_project
sonar.projectName=Demo Project
sonar.projectVersion=1.0

sonar.sources=.
sonar.host.url=http://localhost:9000
sonar.login=your_token_here  # Replace with your real token  
</pre>

Run your analysis
```
sonar-scanner
```

View the SonarQube Report
<pre>
http://localhost:9000/dashboard?id=demo_project  
</pre>
