FROM python

ADD ./app ./app

RUN pip install -r ./app/req.txt

ENTRYPOINT [ "python", "-u", "./app/app.py" ]