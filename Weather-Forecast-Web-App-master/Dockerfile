#FROM python:3.4 as builder

#ADD app /app

# ADD index.html /

# ADD temperature.html /

# ADD requirements.txt /

# ADD templates/ /templates

#COPY requirements.txt /app/requirements.txt

#RUN pip install -r /app/requirements.txt


# RUN pip install requests

from python:3.4-alpine

ADD app /app

COPY requirements.txt /app/requirements.txt

# RUN apk add python3-dev build-base linux-headers pcre-dev

RUN apk add --no-cache uwsgi-python3

# RUN pip install -r /app/requirements.txt

RUN pip install --no-cache-dir -r /app/requirements.txt

#COPY --from=builder /usr/local/lib/python3.4/site-packages /usr/local/lib/python3.4/site-packages



CMD [ "uwsgi", "--http", "0.0.0.0:5000", "--module", "app:flask_app", "--processes", "2", "--threads", "4" ]
