#FROM tensorflow/tensorflow:latest-gpu
#FROM nvcr.io/nvidia/tensorflow:20.03-tf2-py3
#FROM tensorflow/tensorflow:latest-gpu-py3
FROM python:3
MAINTAINER ADAM GREEN

COPY requirements.txt requirements.txt

RUN apt-get update && apt-get install -y \
    build-essential \
    wget \
    python3-pip 

RUN pip3 install --upgrade pip &&\
    pip3 install -r requirements.txt 

#CMD ["bash","call_defect.sh"]
EXPOSE 8000

WORKDIR /work
ENV HOME /work
ENV PYTHONUNBUFFERED=1
#RUN export PATH=$PATH:/app/src/data && echo "export PATH=$PATH" >> /etc/bash.bashrc


#CMD ["bash"]
#CMD ["uvicorn", "ml:app", "--host", "0.0.0.0", "--reload"]
CMD ["python", "app.py"]
