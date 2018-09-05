FROM python:3.4-alpine

ADD app.py /

# ADD index.html /

# ADD temperature.html /

# ADD requirements.txt /

ADD templates/ /templates

RUN pip install -r /templates/requirements.txt

RUN pip install requests

CMD [ "python", "./app.py" ]
