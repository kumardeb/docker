# docker-for-dev

└── python-app
    ├── Dockerfile
    └── src
        ├── req.txt
        └── server.py



FROM python:3.6

# Create app directory
WORKDIR /app

# Install app dependencies
COPY src/req.txt ./

RUN pip install -r req.txt

# Bundle app source
COPY src /app

EXPOSE 8080
CMD [ "python", "server.py" ]
