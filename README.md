# Link: https://www.programonaut.com/setup-ssl-with-docker-nginx-and-lets-encrypt/

# Install docker: https://docs.docker.com/engine/install/ubuntu/

# Steps:
- `cd ~`
- `git clone https://github.com/anhttok/docker-letsencrypt.git ./letsencrypt`
- `sudo docker compose run --rm certbot certonly --webroot -w /var/www/certbot --force-renewal --email {email} -d {domain} --non-interactive --agree-tos`
- ssl files:
  ```
  ssl_certificate     : ~/letsencrypt/certbot/conf/live/{domain}/fullchain.pem;
  ssl_certificate_key : ~/letsencrypt/certbot/conf/live/{domain}/privkey.pem;
  ```
- 
# Notes:
- recreate the container: `sudo docker compose up -d nginx`
- stop: `sudo docker compose down`