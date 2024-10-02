FROM python:3.11-slim

WORKDIR /app/backend

# Copia o requirements.txt e instala as dependências
COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

# Copia o script wait-for-it.sh e da permissão de execução ao script
COPY wait-for-it.sh /wait-for-it.sh
RUN chmod +x /wait-for-it.sh

EXPOSE 5000