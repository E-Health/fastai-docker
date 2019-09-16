FROM continuumio/miniconda3

RUN mkdir /code

WORKDIR /code

COPY . /code/

RUN conda install -n base -c anaconda -c conda-forge -c akode --file /code/requirements.txt

RUN apt-get update \
    && apt-get -y install build-essential cmake

RUN pip install --no-deps face_recognition && \
    conda clean --all --yes

RUN apt-get -qq -y remove cmake \
    && apt-get -qq -y autoremove \
    && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/* /var/log/dpkg.log

RUN echo "conda activate base" >> ~/.bashrc
