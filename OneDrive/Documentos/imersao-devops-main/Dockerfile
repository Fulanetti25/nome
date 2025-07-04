# 1. Use uma imagem oficial do Python como imagem base.
# python:3.11-slim é uma boa escolha por ser leve e estável.
FROM python:3.11-slim

# 2. Define o diretório de trabalho dentro do contêiner.
WORKDIR /app

# 3. Copia o arquivo de dependências para o diretório de trabalho.
# Fazer isso antes de copiar o resto do código aproveita o cache do Docker.
COPY requirements.txt .

# 4. Instala as dependências definidas no requirements.txt.
# --no-cache-dir: Desabilita o cache do pip, o que reduz o tamanho da imagem.
# --upgrade pip: Garante que estamos usando a versão mais recente do pip.
RUN pip install --no-cache-dir --upgrade pip -r requirements.txt

# 5. Copia o restante do código da aplicação para o diretório de trabalho.
COPY . .

# 6. Expõe a porta em que a aplicação será executada.
EXPOSE 8000

# 7. Define o comando para executar a aplicação quando o contêiner iniciar.
# Usamos 0.0.0.0 para tornar a aplicação acessível de fora do contêiner.
CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]

# construir: docker build -t "nome" .
# rodar: docker run -p 8000:8000 "nome"
# localhost:8000/docs

# palavra chave AULA 1: MARVEL
# palavra chave AULA 2: ELLIS