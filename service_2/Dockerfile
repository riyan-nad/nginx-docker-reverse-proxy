FROM python:3.9-slim
WORKDIR /app
COPY app.py .
RUN apt-get update && apt-get install -y curl build-essential python3-dev && pip install uv && uv pip install flask --system
EXPOSE 8002
CMD ["python", "app.py"]