FROM python:3.12-slim
RUN pip install uv 
WORKDIR /app
COPY pyproject.toml uv.lock /app/ 
RUN uv sync

COPY app.py .
EXPOSE 8002
CMD ["uv", "run", "app.py"]