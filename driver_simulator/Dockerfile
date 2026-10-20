# driver_simulator/Dockerfile
FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /app

# COPY requirements.txt .
# RUN pip install --no-cache-dir -r requirements.txt

COPY requirements.txt .
ARG PIP_INDEX_URL=https://mirror-pypi.runflare.com/simple
ENV PIP_INDEX_URL=${PIP_INDEX_URL}
RUN pip install --no-cache-dir -r requirements.txt

COPY simulator.py .

# The command will be provided by docker-compose
ENTRYPOINT ["python", "simulator.py"]