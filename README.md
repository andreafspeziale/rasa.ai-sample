# RASA.AI

## Requirements

    - python
    - pip
    - virtualenv
    - curl

## Install

    - $ virtualenv env
    - $ source env/bin/activate
    - $ pip install -r requirements.txt

## Create models from training data

    - edit config_spacy.json passing as "data" your training data
    - $ python -m rasa_nlu.train -c config_spacy.json

This will create a openmaker folder with model data

## Serve

    - python -m rasa_nlu.server -c ./config_spacy.json

This will start a server listening on port 5000

## Try

    - curl -XPOST localhost:5000/parse -d '{"q":"Who likes javascript?"}' | python -mjson.tool

Magic
