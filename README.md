# ETL Tool - Unstructured Data Extraction, Transformation and Loading Engine with NoSQL Integration

This project is a robust and comprehensive Java application to extract unstructured data from the NewsAPI, transform it by cleaning the data and upload it to the MongoDB NoSQL Database. It contains a three-tiered code structure (Code A -> Code B -> Code C) to initiate an automated workflow for data extraction, processing, and transformation. Code A extracts the data from the NewsAPI based on the pre-defined keyword. Code B receives raw data from the Extraction Engine, automatically writes news contents and titles to files, and manages the storage of data in an organized manner. Code C performs data cleaning and transformation, including the removal of special characters, URLs, and emoticons through self-designed regular expression logic. A NoSQL database, MongoDB is integrated, to store the transformed data from Code C into a designated database named `myMongoNews`. This is an automated data processing workflow, eliminating manual interventions and improving data consistency and accuracy.

## IDE Information

- This application has been developed using `VSCode` as the IDE.
- A Maven Java project was selected as the template to start this project to add the dependency for `MongoDB`.
- The two folders were generated by default: `src` and `target`.

## Java Information

- Java Version: `19.0.1`
- Maven Compiler Source: `1.7`
- Maven Compiler Target: `1.7`

## Folder Structure

The workspace contains two folders by default, where:

- `src`: the folder to maintain sources
- `target`: the folder to maintain class files

Meanwhile, the compiled output files will be generated in the `target` folder by default.

The folder `newsAPIData` contains output files which are generated after getting the response from the API.

## General Information

- `App.java` is the default app which will run and call the subsequent classes and methods.
- All the generated files via code, will be stored in the root directory.
- The files generated by code to store data from `NewsAPI` will be stored in `newsAPIData` folder.

## Project Information

- The `.env` file contains the type of API call to be initiated. For eg.: `everything` or `top-headlines`.
  &nbsp; _Note: To switch between the 2 API calls, take reference of the following code and do not the change the name of the key in the `.env` file._

  Example:

  ```java
        API_KEY=<YOUR_NEWSAPI_API_KEY>
        API_TYPE=top-headlines
  ```

  OR

  ```java
        API_KEY=<YOUR_NEWSAPI_API_KEY>
        API_TYPE=everything
  ```

- There are three main classes and one launcher class as follows:
  - `App.java` - Launches the main class
  - `ExtractionEngine.java` - This class fetches the data from the API and passes it onto the data processing engine.
  - `DataProcessingEngine.java` - This class processes and gets the relevant information from the data passed from first class and stores it into files.
  - `TransformationEngine.java` - This class reads the data stored in the files, cleans the data and uploads it into MongoDB.
