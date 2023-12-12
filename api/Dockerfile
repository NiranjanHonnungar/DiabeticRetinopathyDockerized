FROM python:3.9
WORKDIR /app

ENV FLASK_APP=api.py

COPY ./requirements.txt .

RUN pip install -r requirements.txt

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:5000","api:app"]

