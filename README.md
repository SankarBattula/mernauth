# Add User
$apt update && apt upgrade
$adduser mernweb 
$usermod -aG sudo mernweb 
$groups mernweb 
$su - mernweb 

# Install Node JS
https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04

# App Setup
$mkdir apps
$cd apps
$git cline URL
$ceate .env file
$npm i
$cd frontend
$npm i
$npm run build


# Install PM2 to make app running in the backend
$sudo npm i -g pm2
$pm2 start backend/server.js
$sudo ufw enable
$sudo ufw allow ssh
$sudo ufw allow http
$sudo ufw allow https
$sudo apt install nginx

# Run on port 80

sudo vi /etc/nginx/sites-available/default
server_name abc.com www.abc.com;

proxy_pass http://localhost:5000;
proxy_http_version 1.1;
proxy_set_header Upgrade $http_upgrade;
proxy_set_header Connection 'upgrade';
proxy_set_header Host $host;
proxy_cache_bypass $http_upgrade;
sudo service nginx restart
sudo nginx -t

# to install Certbot
https://www.linode.com/docs/guides/secure-http-traffic-certbot/
