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

# A porta 3306 é definida por padrão para bancos de dados MYSQL
CMD ["/wait-for-it.sh", "db:3306", "--timeout=60", "--","python","app.py"]

# "/wait-for-it.sh": Script usado para aguardar a disponibilidade de outro serviço (neste caso, o banco de dados MySQL).
# "db:3306": Especifica o host  e a porta onde o banco de dados MySQL está rodando. 
# "--timeout=60": Define um tempo limite de 60 segundos para aguardar a disponibilidade do banco de dados. 
# "--": Separa os comandos que o script wait-for-it.sh executará
