FROM python:3.6-slim

ENV PYTHONUNBUFFERED 1

COPY ./requirements.txt requiremrnts.txt
COPY ./app /app
COPY ./entrypoint.sh entrypoint.sh

# install psycopg2
RUN apt-get update && apt-get install -qq -y \
 build-essential libpq-dev netcat --no-install-recommends

RUN pip install -r requiremrnts.txt

WORKDIR /app

RUN adduser --disabled-password --gecos '' user
# RUN chmod -R user:user /app/static
# RUN chmod -R 755 /app/static

USER user

ENTRYPOINT [ "sh", "/entrypoint.sh" ]
