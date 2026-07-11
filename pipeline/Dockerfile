

FROM python:3.13.11-slim
COPY --from=docker.io/astral/uv:latest /uv /uvx /bin/

WORKDIR /code 
ENV PATH /code/.venv/bin:$PATH
COPY pyproject.toml .python-version uv.lock ./
RUN uv sync --locked


COPY pipeline.py .

ENTRYPOINT ["python", "pipeline.py"]