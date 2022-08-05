FROM 763104351884.dkr.ecr.us-west-2.amazonaws.com/tensorflow-training:1.15.2-gpu-py36-cu100-ubuntu18.04

RUN apt-key del A4B469963BF863CC

RUN wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-keyring_1.0-1_all.deb
RUN rm /etc/apt/sources.list.d/cuda.list && rm /etc/apt/sources.list.d/nvidia-ml.list && dpkg -i cuda-keyring_1.0-1_all.deb

RUN apt update
RUN apt install -y python3-opencv
RUN /usr/bin/python3 -m pip install --upgrade pip

RUN pip install awscli
RUN pip install boto3
RUN pip install ujson==1.35
RUN pip install opencv-python==4.1.0.25
RUN pip install Cython==0.28.4
RUN pip install pycocotools==2.0.1
RUN pip install matplotlib==3.0.3
RUN pip install markdown==3.1

RUN git clone https://github.com/tensorpack/tensorpack.git /tensorpack
RUN cd /tensorpack && git fetch origin db541e8ec9edeeb12f8dcc79f3ca835412d282e1 
RUN cd /tensorpack && git reset --hard db541e8ec9edeeb12f8dcc79f3ca835412d282e1 
RUN pip install -e /tensorpack