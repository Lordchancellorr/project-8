## Documentation of Project 8

- CONFIGURATION OF APACHE AS A LOAD BALANCER
I created an ubuntu server 20.04 for this project and named it Project-8-apache-lb- ![Project-8-apache-lb](https://github.com/Lordchancellorr/project-8/blob/main/Images/instances.PNG)
Then I opened a TCP port 80 in the inbound rules.

- I installed Apache Load Balancer on `Project-8-apache-lb` server and configured it to point traffic coming to Load balancer to both Web Servers. Then i run the following commands to install apache2 and its dependencies on the project 8 terminal:
`sudo apt update` `sudo apt install apache2 -y` `sudo apt-get install libxml2-dev` `sudo a2enmod rewrite` `sudo a2enmod proxy` `sudo a2enmod proxy_balancer` `sudo a2enmod proxy_http` `sudo a2enmod headers` `sudo a2enmod lbmethod_bytraffic` theni restarted apache with `sudo systemctl restart apache2` see the image below; ![Apache2 and its dependencies](https://github.com/Lordchancellorr/project-8/blob/main/Images/apache2%20Dependencies.PNG)
then i confirmed the status with `sudo systemctl status apache2` see the image below ![Apache2 status](https://github.com/Lordchancellorr/project-8/blob/main/Images/apache2%20status.PNG)

I configured the load balacing, entered some codes into the `vi /etc/apache2/sites-available/000-default.conf` file, inserted the two webservers private internet protocol addresses then verified the conneection and successful configuration using the load Balancer's (Project-8) public IP plus /index.php and the image below was the result. ![Load Balancer](https://github.com/Lordchancellorr/project-8/blob/main/Images/php.PNG)

I opened two SSH consoles for both Web Servers and run this command: `sudo tail -f /var/log/httpd/access_log` refreshed the webservers pages respectively and the images below were the output on the terminals: ![access log for webserver 1](https://github.com/Lordchancellorr/project-8/blob/main/Images/access%20log%20for%20webserver1.PNG) ![access log for webserver 2](https://github.com/Lordchancellorr/project-8/blob/main/Images/access%20log%20webserver2.PNG)

In the `vi /etc/hosts` file, i edited and replaced the local IP address numbers with web1 and web2 respectively
Check the images below for Propitix Webserver 1 and 2
![Webserver 1](https://github.com/Lordchancellorr/project-8/blob/main/Images/Webserver1.PNG)
![Webserver 2](https://github.com/Lordchancellorr/project-8/blob/main/Images/Webserver2.PNG)

Thank you!
