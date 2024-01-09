https://goauthentik.io/docs/installation/docker-compose

wget https://goauthentik.io/docker-compose.yml

sudo apt-get install -y pwgen

echo "PG_PASS=$(pwgen -s 40 1)" >> .env
echo "AUTHENTIK_SECRET_KEY=$(pwgen -s 50 1)" >> .env

echo "AUTHENTIK_ERROR_REPORTING__ENABLED=true" >> .env

docker compose up -d


http://89.117.60.25:9000/if/flow/initial-setup/