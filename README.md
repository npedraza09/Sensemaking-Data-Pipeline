<a href="https://npedraza09.github.io">Back to My Portfolio</a>

# Sensemaking Data Pipeline

This project is designed to scrape, clean, and structure MIT course catalog data for word-frequency analysis while showcasing a fully containerized and orchestrated workflow. Leveraging Python’s urllib and BeautifulSoup for web scraping, the pipeline transforms raw HTML into structured data and then processes it through Docker and Airflow to ensure efficient and modular task execution. The resulting JSON word counts feed into an interactive JavaScript and D3-based bubble chart, providing a visually engaging overview of course content trends. By integrating Python-driven data ingestion and transformation with front-end data storytelling, this project demonstrates an end-to-end solution for extracting insights from unstructured web data.


## Steps to run the pipeline
1. Either fork or download the folder in this repository and open it in your code editor
2. Install all necessary dependencies on your machine
3. If you want to generate your own words.js file, do the following:
  - In your terminal, inside the airflow-docker folder, run `docker compose up` to create and run the containers
  - Open a browser window and navigate to https://localhost:8080/. You should arrive at the Airflow login page. Enter “airflow” for both the username and password
  - Select the assignment.py DAG and switch to the Graph View. Select each task and then select Run
  - Your DAG will generate a words.json file located on the worker_1 airflow server
  - Transfer the words.json file as a .js file to your local machine
  - In your words.js file, make the word count list equal to a dictionary named "scores"
4. Navigate to file:///YOUR_PATH_HERE/SensemakingDataPipeline/code_visualization/mitcourses_graph.html in your web browser and check out the results

## Features
- Full ETL pipeline in Airflow
- Interactive bubble chart providing visual results of the word count

  ## Future Features
- Choose your own theme from the D3 library
- Add other metrics for the data

## Tools:
* Python
* JavaScript
* HTML
* JSON
* Airflow
* Libraries: urllib, BeautifulSoup, os, D3, and airflow

## What the project looks like

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/3fa4e5be-5de2-4ef3-a77c-9b2e0ba0f9cb" />

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/9c2f81b9-a4f2-4334-ae20-9545d109443b" />





