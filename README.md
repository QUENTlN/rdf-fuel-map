
# RDF fuel map France

This project uses the French gas station data provided by [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/prix-des-carburants-en-france-flux-instantane/) to convert them into RDF format and run them on a SPARQL server. This project provides a map to visualize gas station information.


## Installation

Launch the SPARQL server

```bash
  cd apache-jena-fuseki-4.8.0
  ./fuseki-server
```

Open the [map.html](map.html) in browser
## Convert data

To convert the [CSV source file](https://www.data.gouv.fr/fr/datasets/r/64e02cff-9e53-4cb2-adfd-5fcc88b2dc09), you need to run the code blocks in the [semFuel.ipynb notebook](semFuel.ipynb).

This will save the RDF graph in Turtle format in the [stations.ttl](stations.ttl) file.

## Load data in SPARQL server

To load data into a SPARQL server, you can use the Apache Jena Fuseki server, supplied with a persistent database that can be started as explained in the [installation phase](#Installation). Alternatively, you can create a database called **stations** and load the [stations.ttl](stations.ttl) file to supply the data.

## Display data

To display data on a map, open [map.html](map.html) in a browser. Next, load the data either by uploading the [queryResults.json](queryResults.json) file or by clicking on **Import from Fuseki**.

![map image](/images/map.png)

Click on a marker to display details.

![details image](/images/details.png)