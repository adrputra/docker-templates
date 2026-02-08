<!-- Run Migration -->
docker run --rm \
  --network main-dev \
  -e KONG_DATABASE=postgres \
  -e KONG_PG_HOST=postgres \
  -e KONG_PG_PORT=5432 \
  -e KONG_PG_DATABASE=kong \
  -e KONG_PG_USER=admin \
  -e KONG_PG_PASSWORD='Contabo8@adr' \
  kong:3.13 kong migrations up

docker run --rm \
  --network main-dev \
  -e KONG_DATABASE=postgres \
  -e KONG_PG_HOST=postgres \
  -e KONG_PG_PORT=5432 \
  -e KONG_PG_DATABASE=kong \
  -e KONG_PG_USER=admin \
  -e KONG_PG_PASSWORD='Contabo8@adr' \
  kong:3.13 kong migrations finish
