# POET SEARCH ENGINE

## Start the Server

Please install [npm](https://www.npmjs.com/) before running the engine. 
Use the following commands to start the engine.

```bash
# Install required dependencies
npm install

# Start the application 
npm start
# Local:            http://localhost:3000
# On Your Network:  http://192.168.1.101:3000
```

## Software Stack

- BeautifulSoup package for scrapping
- Elasticsearch as the search engine
- Search.UI for frontend templates
- React.js for frontend design
- Node.js for backend design

## Preprocessing

The corpus of the poets were created using the BeautifulSoup. [FamousPoetsAndPoems](http://famouspoetsandpoems.com/poets.html) and [PoetsOrg](https://poets.org/poets) websites are used to collect the data. Since each entry was in English Google Translator from deep_translator is used for translation from English to Sinhala.

The fields scrapped are,
| Field             | Type                              | Description                                           |
| :----------:      | :--------:                        | :-----------------:
| Name	            | Short Text	                    | Name of the poet                                      |
| Birth_year        | Date	                            | Date of birth of the poet                             |
| Death_year        | Date	                            | Date of death of the poet                             |
| Categories        | List of Short Text	            | A list of genres covered by the poet                  |
| Poem              | Long Text	                        | A poem written by poet                                  |
| Bio               | Long Text	                        | A brief description of the poet and his work          |
| Similar_poets     | List of Short Text	            | A list of poets whose work is similar to the poet     |
| Quote	            | Long Text                         | A popular quotation from a popular poem written by the poet   |


290 documents are collected, stemmed, tokenized and indexed using elasticsearch.

## File Structure

    ├── dataset : data scraped from [FamousPoetsAndPoems](http://famouspoetsandpoems.com) and [PoetsOrg](https://poets.org/poets)                   
        ├── poets.json : file consisting of poets data in json format 
        ├── poets.csv : file consisting of poets data in csv format 
    ├── src/config                   
        ├── config helper.js : controller functions
        └── engine.json : configurations
    ├── App.js : the React App  
    ├── package.json : the dependencies
    ├── scraper.py :  source code for the poets data scraper  

## Advanced Features

1. Sorting options are given for the following fields.
- Name
- Birth_year
- Death_year

2. Faceting options are given for the following fields.
- Categories
- Birth_year
- Death_year

3. A UI designed with the templates taken from Search.ui

