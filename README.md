# cookiecutter_sample_9
![Tests](https://github.com/tyo-yo/cookiecutter_sample_9/workflows/Tests/badge.svg)  [![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)


Some description.

## Usage
```shell
git clone https://github.com/tyo-yo/cookiecutter_sample_9.git
cd cookiecutter_sample_9

docker run --rm -it -v $PWD:/cookiecutter_sample_9 --env-file .env --gpus all docker.pkg.github.com/tyo-yo/cookiecutter_sample_9/cookiecutter_sample_9:latest bash
docker run --rm -it -v $PWD:/cookiecutter_sample_9 -p 11111:11111 --env-file .env --gpus all docker.pkg.github.com/tyo-yo/cookiecutter_sample_9/cookiecutter_sample_9:latest streamlit run --server.port 11111 app.py
docker run --rm -it -v $PWD:/cookiecutter_sample_9 -p 11111:11111 --env-file .env --gpus all docker.pkg.github.com/tyo-yo/cookiecutter_sample_9/cookiecutter_sample_9:latest jupyter lab --port=11111 --ip=0.0.0.0 --no-browser --allow-root
```


## Quick Start (for owner)
1. Setup your developemntal environment
  * Using Docker (Recommended):
```
# If you update python dependencies, you should re-build docker image
docker build . -t  tyo-yo/cookiecutter_sample_9/cookiecutter_sample_9
```
  * Using poetry:
    * First, you should install dependencies other than python dependencies like MeCab
    * Install python packages:
```
poetry install
```

2. Create your own .env file and put your secret information like API key

3. Get your code on!
   * Your main component like model should be under ``cookiecutter_sample_9/``
   * Visualization like data analysis can be made by jupyter notebook: ``notebooks/``
   * Dataset should be on cloud like AWS S3 or Google Storage for reproducibility
     * When dataset is too large, consider caching or saving it under ``data/``
   * When writing training code, you should use Comet.ml for managing experiments
     * experimental result like saved model should be under ``experiments/``
   * Some command-line utility like profile your code should be under ``scripts/``
     * [Typer](https://typer.tiangolo.com) would supports building CLI
   * You should write test to make sure there are no bugs: ``tests/``

http://colab.research.google.com/github/tyo-yo/cookiecutter_sample_9/blob/main/notebooks/demo-colab-streamlit.ipynb
