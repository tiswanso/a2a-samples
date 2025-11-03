FROM python:3.13-slim
#FROM python:3.13

COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

# leave to indicate default port (NOTE: the app can listen on any port))
EXPOSE 9999
WORKDIR /app

#COPY . ./
COPY pyproject.toml ./
COPY __init__.py __main__.py agent_executor.py ./


RUN uv sync

ENTRYPOINT ["uv", "run", ".", "--host", "0.0.0.0"]
