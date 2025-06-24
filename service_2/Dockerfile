FROM python:3.9-slim
WORKDIR /app
COPY app.py .
RUN apt-get update && apt-get install -y curl && pip install flask
EXPOSE 8002
CMD ["python", "app.py"]
