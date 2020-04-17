# RasaLit

A collection of [streamlit](https://github.com/streamlit/streamlit) with helper views for Rasa NLU.
Feedback is welcome.

<img src="docs/square-logo.svg" width=200 height=200 align="right">

## Produced

This project was initiated at [Rasa](https://rasa.com) as a fun side project
that supports the research and developer advocacy teams at Rasa.

It is maintained by [Vincent D. Warmerdam](https://twitter.com/fishnets88), Research Advocate at Rasa.

## Installation 

```
python -m pip install git+https://github.com/RasaHQ/rasalit
```

## Usage 

You can directly access the command line app. 

```
> rasalit --help
Usage: rasalit [OPTIONS] COMMAND [ARGS]...

  Helper Views for Rasa NLU

Options:
  --help  Show this message and exit.

Commands:
  overview  Gives an overview of all results generated by `rasa train`.
```

But it may be safer to run like so; 

```
> python -m rasalit overview
  You can now view your Streamlit app in your browser.

  Local URL: http://localhost:8502
  Network URL: http://192.168.1.28:8502
```

## Viewers

The app contains a collection of viewers that each specialize in a seperate task. 

### Overview 

You can run cross validation of pipelines in Rasa via the command line.

```
rasa test nlu --config configs/config-light.yml \
              --cross-validation --runs 1 --folds 2 \
              --out gridresults/config-light
rasa test nlu --config configs/config-heavy.yml \
              --cross-validation --runs 1 --folds 2 \
              --out gridresults/config-heavy
```

Then rasa, in this case, will save the results in `gridresults/config-light` and 
`gridresults/config-heavy` respectively.

To get an overview of all the results in subfolders of  `gridresults`, 
you can run the `rasalit overview` command.
