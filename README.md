# TARA Article Search Demo Application

A web-based search application for TARA acupuncture research literature. This demo app enables researchers, practitioners, and students to search and discover acupuncture research articles using standardized terminology from the TARA Acupoints ontology. It was developed to demonstrate how queries from TARA Acupoints Ontology can enable intelligent semantic search functionalities.

* [About TARA Acupoints Ontology](https://github.com/smtifahim/TARA-Ontology-Repository/tree/master/ontology-files/generated)
* [TARA Acupoints Ontology Repository](https://github.com/smtifahim/TARA-Ontology-Repository/tree/master)

## Demo App Deployed On Netlify

* **Visit the application:** [https://tara-demo.netlify.app/](https://tara-demo.netlify.app/)

## Features

- **Multi-field Search**: Search articles by acupoints, meridians, anatomical locations, health conditions, and more
- **Intelligent Autocomplete**: Smart suggestions with synonym support for Chinese and English terminology for acupoints and syonymous search for other filters.
- **Ontology-based**: Leverages the TARA Acupoints ontology for standardized terminology
- **Responsive Design**: Works seamlessly across desktop and mobile devices

The application allows searching across multiple dimensions including acupoints (English and Chinese names), meridians, special point roles, anatomical regions, health conditions, and clinical studies.

**Technology Stack**: Pure HTML5, CSS3, and vanilla JavaScript frontend with data sourced from SPARQL queries against Stardog triplestore, deployed on Netlify.

## Project Structure and Setup

```
TARA-Demo-App/
├── index.html              # Main application interface
├── script.js               # JavaScript logic and autocomplete functionality
├── styles.css              # Application styling and responsive design
├── tara-logo.png           # TARA project logo
├── json/                   # Data files for the application
│   ├── article-data.json           # Main research article metadata
│   ├── acupoints-synonyms.json     # Acupoint names and synonyms
│   ├── meridians-synonyms.json     # Meridian names and synonyms
│   ├── anatomical-synonyms.json    # Anatomical location synonyms
│   ├── body-regions-synonyms.json  # Body region synonyms
│   └── conditions-synonyms.json    # Health condition synonyms
└── json-data-loader/       # Data management tools
    ├── tara-data-loader.py         # Python script for data updates
    └── sparql-queries/             # SPARQL query files
        ├── article-data.rq
        ├── acupoints-synonyms.rq
        ├── meridians-synonyms.rq
        ├── anatomical-synonyms.rq
        ├── body-regions-synonyms.rq
        └── conditions-synonyms.rq
```

### Local Development

**Prerequisites**: A modern web browser, Python 3.6+ (for data updates), and access to Stardog TARA database (for data management).

1. **Clone and serve:**

   ```bash
   git clone https://github.com/smtifahim/TARA-Demo-App.git
   cd TARA-Demo-App
   python -m http.server 8000  # Or open index.html in browser
   ```
2. **Access:** Navigate to `http://localhost:8000`

## Data Management

After a new release of the TARA Acupoints ontology, run the Python script at `json-data-loader/tara-data-loader.py`. This script executes SPARQL queries against the Stardog endpoint and saves results as JSON files for the application.

**Prerequisites for data updates:**

- Python 3.6+ with Stardog client: `pip install stardog`
- Environment variable `STARDOG_TARA_PASSWORD` set with database password
- Access to TARA Stardog cloud endpoint

**Configuration:**

- Stardog Endpoint: `https://sd-c1e74c63.stardog.cloud:5820`
- Database: `TARA-Acupoints`
- Authentication: Username `TARA` with password from environment variable

**Running the data loader:**

```bash
cd json-data-loader
export STARDOG_TARA_PASSWORD="your-password-here"
python tara-data-loader.py
```

### Sample Output

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

## Contributing and Support

**Contributing:**

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes and push to the branch
4. Open a Pull Request

**Support**: For questions or issues, open a GitHub issue or contact the TARA project team through the [TARA Repository](https://tara-repository.mgb.org/).

**License**: MIT License - see [LICENSE](LICENSE) file for details.

**Author**: Fahim Imam

**Related Projects**: [TARA Acupoints Ontology](https://tara-repository.mgb.org/) and [Stardog](https://www.stardog.com/)
