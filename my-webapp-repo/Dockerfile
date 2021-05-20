# FROM ubuntu:18.04

# # Install dependencies
# RUN apt-get update
# RUN apt-get -y install apache2

# Install apache and write hello world message
# FROM <ACCOUNT-ID>.dkr.ecr.<REGION>.amazonaws.com/<BASE-REPO-NAME>
FROM 000000000000.dkr.ecr.us-west-2.amazonaws.com/gold-repo
    
RUN echo '<html> <head> <title>Amazon ECS</title> <style>body {margin-top: 40px; background-color:blue;} </style> </head><body> <div style=color:white;text-align:center> <h1>Congratulations!!!</h1> <h2>Your application is now running on a container in Amazon ECS using a base image from ECR</h2> </div></body></html>' > /var/www/html/index.html

# Configure apache
RUN echo '. /etc/apache2/envvars' > /root/run_apache.sh && \
 echo 'mkdir -p /var/run/apache2' >> /root/run_apache.sh && \
 echo 'mkdir -p /var/lock/apache2' >> /root/run_apache.sh && \ 
 echo '/usr/sbin/apache2 -D FOREGROUND' >> /root/run_apache.sh && \ 
 chmod 755 /root/run_apache.sh

EXPOSE 80 8080

CMD /root/run_apache.sh