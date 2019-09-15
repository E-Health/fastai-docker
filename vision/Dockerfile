FROM continuumio/miniconda3

RUN mkdir /code

WORKDIR /code

COPY . /code/

RUN conda env create -f /code/conda_environment.yml && \
	conda install -n fastai-vision -c conda-forge -c pytorch -c fastai --no-deps --file /code/requirements.txt && \
    conda clean --all --yes

RUN echo "conda activate fastai-vision" >> ~/.bashrc
