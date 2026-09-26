FROM ubuntu

WORKDIR /app

COPY requirements.txt /app/
COPY devops /app/

RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y python3 python3-pip python3-venv && \
    rm -rf /var/lib/apt/lists/*

RUN python3 -m venv venv1 && \
    ./venv1/bin/pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

CMD ["/app/venv1/bin/python3", "manage.py", "runserver", "0.0.0.0:8000"]
