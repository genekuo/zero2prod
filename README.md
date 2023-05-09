curl -i -X POST -d 'email=thomas_mann@hotmail.com&name=Tom' \
http://127.0.0.1:8000/subscriptions

docker build --tag zero2prod --file Dockerfile .
docker run -p 8000:8000 zero2prod

curl -v http://127.0.0.1:8000/health_check
curl -v http://127.0.0.1:8000/health_check

curl POST \
    --data 'name=lee%20guin&email=ursula_lee_guin%40gmail.com' \
    127.0.0.1:8000/subscriptions --verbose
