# FROM use the exact version
# WORKDIR define where the container will works
# COPY, copy the dependecies's file in the container
# RUN install all dependecies in the requirements.txt without using the cache
# COPY copy all the projects files in the containers
# EXPOSE port listening
# CMD its the commande which execute the container a the start

FROM python:3.10-slim
WORKDIR /app
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
COPY . /app
EXPOSE 80
CMD [ "python", "app.py" ]
