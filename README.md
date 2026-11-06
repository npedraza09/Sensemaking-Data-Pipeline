# Sensemaking Data Pipeline

An Airflow pipeline that scrapes MIT's course catalog, cleans the course titles and counts word frequency, then shows the result as an interactive D3 bubble chart. Built for my MIT Professional Certificate in Data Engineering (2024–2025).

## How it works

The DAG in `SensemakingDataPipeline/airflow-docker/dags/assignment.py` runs these steps in order:

1. **Catalog:** download each catalog page listed in `urls.txt` (urllib).
2. **Combine:** merge the pages into one file.
3. **Titles:** extract the course titles (the `<h3>` tags) with BeautifulSoup and save them as JSON.
4. **Clean:** remove punctuation, numbers and one-letter words.
5. **Count words:** count how often each word appears and save `words.json`.

`code_visualization/mitcourses_graph.html` reads those counts and draws the bubble chart.

**Built with:** Python, Apache Airflow, Docker, BeautifulSoup, JavaScript, D3.js

## Run it locally

You need Docker.

1. From `SensemakingDataPipeline/airflow-docker/`, run `docker compose up`.
2. Open http://localhost:8080 and sign in to Airflow (username and password `airflow`).
3. Open the `Project` DAG (defined in `assignment.py`), switch to Graph view and run each task in order.
4. Copy `words.json` from the Airflow worker to `code_visualization/words.js`, setting the word counts to a variable named `scores`.
5. Open `code_visualization/mitcourses_graph.html` in your browser.

## Screenshots

<img width="800" height="400" alt="Sensemaking Data Pipeline screenshot" src="https://github.com/user-attachments/assets/3fa4e5be-5de2-4ef3-a77c-9b2e0ba0f9cb" />

<img width="800" height="400" alt="Sensemaking Data Pipeline screenshot" src="https://github.com/user-attachments/assets/9c2f81b9-a4f2-4334-ae20-9545d109443b" />
