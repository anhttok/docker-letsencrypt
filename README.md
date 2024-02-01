# Link: https://www.programonaut.com/setup-ssl-with-docker-nginx-and-lets-encrypt/

# Install docker: https://docs.docker.com/engine/install/ubuntu/

# Steps:
- `cd ~`
- `git clone https://github.com/anhttok/docker-letsencrypt.git ./letsencrypt`
- `sudo docker compose up -d`
- `sudo docker compose run --rm certbot certonly --webroot -w /var/www/certbot --force-renewal --email {email} -d {domain} --non-interactive --agree-tos`
- `sudo docker compose down`

# Test
- `cd ~/letsencrypt/test`
- `sudo docker compose up -d`
- Stop after testing `sudo docker compose down`

# Notes:
- recreate the container: `sudo docker compose up -d nginx`
- stop: `sudo docker compose down`

# Todo:
- Add script to auto renew