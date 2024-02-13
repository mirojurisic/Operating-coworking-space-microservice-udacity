# https://www.freecodecamp.org/news/how-to-dockerize-a-flask-app/
# syntax=docker/dockerfile:1

FROM python:3.12.2-alpine

ARG DB_HOST_URL
ENV DB_HOST=${DB_HOST_URL}

ARG DB_USERNAME
ENV DB_USERNAME=${DB_USERNAME}

ARG DB_PASSWORD
ENV DB_PASSWORD=${DB_PASSWORD}


ARG DB_NAME
ENV DB_NAME=${DB_NAME}

WORKDIR /analytics

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY . .

CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]

# docker build --build-arg=DB_HOST_URL=http://localhost:5432  --build-arg=DB_USERNAME=ADMIN --build-arg=DB_PASSWORD=ADMIN --tag python-docker .
# docker run -d -p 5000:5000 python-docker
