curl -i -X POST -d 'email=thomas_mann@hotmail.com&name=Tom' \
http://127.0.0.1:8000/subscriptions

docker build --tag zero2prod --file Dockerfile .
docker run -p 8000:8000 zero2prod

curl -v http://127.0.0.1:8000/health_check
curl -v http://127.0.0.1:8000/health_check

curl POST \
    --data 'name=lee%20guin&email=ursula_lee_guin%40gmail.com' \
    127.0.0.1:8000/subscriptions --verbose


## Sign up DO
https://cloud.digitalocean.com/registrations/new

## Installing doctl
https://docs.digitalocean.com/reference/doctl/how-to/install/

## Edit sepc.yaml

## Authenticating DO
doctl auth init
## Linking your github account
https://docs.digitalocean.com/support/how-to-troubleshoot-apps-in-app-platform/

## Creating an application
doctl apps create --spec spec.yaml
## Check your app status
doctl apps list
DO dashboard: https://cloud.digitalocean.com/login

## Retrieving the public URI
doctl apps list
## Update app specification
doctl apps update [YOUR-APP-ID] --spec=spec.yaml

## Add a Trusted Source using the Control Panel

## Migrating the database
DATABASE_URL=YOUR-DO-DB-CONNECTION-STRING sqlx migrate run

## Testing
curl POST \
    --data 'name=le%20guin&email=ursula_le_guin%40gmail.com' \
    [public URI]/subscriptions --verbose

## Delete app
doctl apps delete [YOUR-APP-ID]