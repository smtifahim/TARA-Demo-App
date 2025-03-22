# TARA Ariticle Search Demo Application

A demo article search app for TARA acupuncture research, built using HTML and JavaScript. The app is currently deployed on Netlify.

* Visit the app from [https://tara-demo.netlify.app/](https://tara-demo.netlify.app/)

## JSON Data Loader

After a new release of the TARA Acupoints ontology, run the Python script at `json-data-loader/tara-data-loader.py`. This script executes a set of SPARQL queries (located in `json-data-loader/sparql-queries`) against the Stardog endpoint and saves the query results as corresponding JSON files required for the TARA Article Search application.  

### Sample Execution

```
json-data-loader % python tara-data-loader.py

Program execution started...

Step 0: Checking Stardog server status..
        Server Status: Stardog server is running and able to accept traffic.
Step 0: Done!

Step 1: Executing query from: ./sparql-queries/article-data.rq
        Saving query results...
        Query results saved to: ../json/article-data.json
Step 1: Done!

Step 2: Executing query from: ./sparql-queries/acupoints-synonyms.rq
        Saving query results...
        Query results saved to: ../json/acupoints-synonyms.json
Step 2: Done!

Step 3: Executing query from: ./sparql-queries/meridians-synonyms.rq
        Saving query results...
        Query results saved to: ../json/meridians-synonyms.json
Step 3: Done!

Step 4: Executing query from: ./sparql-queries/anatomical-synonyms.rq
        Saving query results...
        Query results saved to: ../json/anatomical-synonyms.json
Step 4: Done!

Step 5: Executing query from: ./sparql-queries/body-regions-synonyms.rq
        Saving query results...
        Query results saved to: ../json/body-regions-synonyms.json
Step 5: Done!

Step 6: Executing query from: ./sparql-queries/conditions-synonyms.rq
        Saving query results...
        Query results saved to: ../json/conditions-synonyms.json
Step 6: Done!

All queries executed and results are saved successfully!
```
