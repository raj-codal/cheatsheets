installing java: https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-get-on-ubuntu-16-04


config java: sudo update-alternatives --config java

Generating the jar:
  mvn clean install

nohup java -jar appointmentmaker-0.0.1-SNAPSHOT.jar> nohup.log &

to stop:
  fuser -k -n tcp 8080


Server Script:

#shell script
<pre>
  #git clone https://github.com/dhananiraj/builds.git
  cd ./builds
  git pull origin master
  fuser -k -n tcp 8080
  nohup java -jar *.jar> nohup.log &
</pre>

Development Script:

#shell script
<pre>
  mvn clean install
  cd ./target
  git clone https://github.com/dhananiraj/builds.git
  cp *.jar ./builds
  cd ./builds
  git add .
  git commit -m "update"
  git push origin master
  #pause
</pre>
