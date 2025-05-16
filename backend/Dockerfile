FROM python:3.12-slim

WORKDIR /app

RUN apt update

RUN apt install curl -y

RUN pip install poetry

COPY . .

RUN poetry install

EXPOSE 8000

#CMD ["poetry", "run", "uvicorn", "app.main:app", "--reload", "--host", "0.0.0.0", "--port", "8000"]

CMD ["sh", "-c", "poetry run bash ./prestart.sh && poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload"]
