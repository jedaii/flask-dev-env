FROM python:3.9
RUN groupadd -r uwsgi && useradd -r -g uwsgi uwsgi
RUN mkdir app
WORKDIR ./app
COPY /docker/python/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY /app /app
COPY docker/python/cmd.sh /
EXPOSE 5000
USER uwsgi
CMD ["/cmd.sh"]