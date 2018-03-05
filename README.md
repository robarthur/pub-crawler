# pub-crawler

A travelling salesman problem, with beer!  🍺 

## Introduction

This is a simple travelling salesman problem implemented with Pandas/Numpy using a dataset from Kaggle.

The dataset contains the [geolocation of 51,[566 pubs in the UK known to the Food Standards Agency](https://www.kaggle.com/rtatman/every-pub-in-england)

Using this dataset we're designing a pubcrawl for an an arbitrary postcode area (e.g. NW1).

The route is calculated using the 'Euclidian distance' as the crow flies between establishments and a [two opt algorithm](https://en.wikipedia.org/wiki/2-opt) to determine the optimum route.

## Getting started

The only dependency is Docker.  This paticular project uses a custom docker image based on the [Jupyter Opinionated Docker Stacks](https://github.com/jupyter/docker-stacks) 

This image can be built at the root of the project running:

`docker build -t scipy-mapping-test .`

Once that build is complete, the jupyter notebook can be run by running

`docker-compose up`

This will present a URL which can be used to access the Jupyter notebook.

Once I've got this tidied up I'll publish as a kernel on Kaggle.

## Future improvements

This is a really basic POC.  Some things I'd like to look at in the future:

- Animating the two-opt algorithm on a map/plot.  I think it would be great to be able to visualise the decision making process by the algorthim.
- Use something like the Google direction API to optimised the distance calculation.  Rather than an 'as the crow flies' Euclidian distance what about the distance to walk.
- Better yet, don't optimise for distance, optimise for time.  There's lots of ways to get between pubs - buses, tubes, taxis, walking.  We can make this a multi dimensional problem.
- Enhance the data that's available with something like the Google Place API. More data is better.  No one wants to turn up to the pub to find it shut on weekends, or closed down a year ago!