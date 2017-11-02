# RASA.AI

## Requirements

    - macos
    - python
    - pip
    - virtualenv
    - curl
    - brew install XZ (for mac)

## Install

    - $ virtualenv env
    - $ source env/bin/activate
    - $ pip install -r requirements.txt
    - $ python -m spacy download en

## Create models from training data

    - edit config_spacy.json passing as "data" your training data
    - $ python -m rasa_nlu.train -c config_spacy.json --fixed_model_name current

This will create a openmaker folder with model data

## Serve

    - python -m rasa_nlu.server -c ./config_spacy.json

This will start a server listening on port 5000

## Try

    - curl -XPOST localhost:5000/parse -d '{"q":"Who likes javascript?"}' | python -mjson.tool

Magic

# MOODBOT

This repository contains also the rasa.ai CORE package.
A simple sample can be found with comments in the MOODBOT folder.

## Train MOODBOT

    - $ cd moodbot
    - $ python -m rasa_nlu.train -c nlu_model_config.json --fixed_model_name current

## Train the dialogue model

    - $ python -m rasa_core.train -s data/stories.md -d domain.yml -o models/dialogue
    - $ python -m rasa_core.run -d models/dialogue -u models/nlu/current

## Sories viz

    - $ brew install graphviz
    - $ pip install pygraphviz --install-option="--include-path=/usr/include/graphviz" \
  --install-option="--library-path=/usr/lib/graphviz/"
    - $ python -m rasa_core.visualize -d domain.yml -s data/stories.md -o graph.png
