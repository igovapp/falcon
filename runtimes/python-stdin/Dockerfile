FROM python:3.13

ADD https://raw.githubusercontent.com/starjuice/wait-for-entrypoint/v0.1.0/wait-for-entrypoint.sh /opt/docker-entrypoint.sh
RUN chmod +x /opt/docker-entrypoint.sh


RUN pip install pytest
WORKDIR /app
RUN mkdir -p /opt
ADD run.sh /opt/
ADD runtests.py /opt/
ADD modes /opt/modes/
RUN chmod +x /opt/run.sh
RUN chmod 755 -R /opt/modes
# COPY sitecustomize.py /usr/local/lib/python3.13/
RUN ls -al /opt
ENTRYPOINT ["/opt/run.sh"]
# ENTRYPOINT ["/opt/docker-entrypoint.sh"]
