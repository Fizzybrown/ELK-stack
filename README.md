# Elasticsearch-logstash-Kibana-Docker-Compose
Create ELK stack using Docker Compose
#install filebeat
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-7.x.list
sudo apt-get update
sudo apt-get install filebeat

#install nginx


sudo apt install nginx


#activate the nginx module


sudo filebeat modules list
ls /etc/filebeat/modules.d/
sudo filebeat modules enable nginx
sudo systemctl restart filebeat

#configure the filebeat.yml file

sudo vi /etc/filebeat/filebeat.yml 

#under filebeat input change the path to the directory where your log file is located 

#then restart the filebeat  
sudo systemctl restart filebeat
