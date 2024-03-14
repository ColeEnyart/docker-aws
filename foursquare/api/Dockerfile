FROM python:3.7-alpine
WORKDIR /usr/src/app

# COPY ./ ./

RUN apk update \
    && apk add postgresql-dev gcc python3-dev musl-dev git --no-cache

RUN git init

RUN git pull https://github.com/ColeEnyart/docker-aws

WORKDIR /usr/src/app/foursquare/api

RUN pip3 install -r requirements.txt

CMD ["flask", "run", "--host=0.0.0.0", "--port=80"]

# docker build --platform=linux/amd64 -t username/foursquare_backend .
# docker run -p 80:80 username/foursquare_backend
# http://localhost/locations

# docker push username/foursquare_backend
# docker run -e FLASK_ENV=development -p 80:80 -v /$PWD:/usr/src/app username/foursquare_backend

# docker build --no-cache -t username/foursquare_backend:v1 .
# docker push username/foursquare_backend:v1