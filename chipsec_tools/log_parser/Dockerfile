FROM ubuntu:latest@sha256:1e622c5f073b4f6bfad6632f2616c7f59ef256e96fe78bf6a595d1dc4376ac02

RUN apt-get update -y && \
    apt-get install -y python3.8-dev python3.8 python3.8-distutils curl

RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
RUN python3.8 get-pip.py 
copy ./requirements.txt /app/requirements.txt

WORKDIR /app

RUN pip3.8 install -r requirements.txt

COPY . /app

ENV LC_ALL=en_CA.UTF-8
ENV LANG=en_CA.UTF-8
ENV LANGUAGE=en_CA.UTF-8

ENTRYPOINT [ "flask" ]

CMD [ "run", "--host", "0.0.0.0", "--port", "8080"]
