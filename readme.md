# Project: Premier League 2023-2024 Odds Analysis

## Table of Contents

1. [Project Overview](#project-overview)
2. [Goals](#goals)
3. [Setup](#setup)
   - [Running the Notebook Locally with Jupyter Lab](#running-the-notebook-locally-with-jupyter-lab)
   - [Running the Notebook Online with Google Colab](#running-the-notebook-online-with-google-colab)
4. [Running the Project](#running-the-project)
5. [Challenges](#challenges)
6. [Acknowledgments](#acknowledgments)
7. [License](#license)

## Project Overview

This project aims to analyze match odds data for the 2023-2024 English Premier League (EPL) season to determine the most profitable betting strategy purely based on odds. The analysis will compare profit and loss for various betting scenarios including:

- Home Win: Betting on the home team to win.
- Draw: Betting on the match to end in a draw.
- Away Win: Betting on the away team to win.
- Favorite: Betting on the outcome with the lowest odds (the favorite).
- Underdog: Betting on the outcome with the highest odds (the underdog).
- Random Selections: Generating five sets of random match outcome selections (home win, draw, away win) for every game of the season.

By evaluating these scenarios, we aim to identify which betting strategy, if any, offers the best potential for profitability based on historical odds data. As you will see, it's not easy to earn a profit from the bookies—they've got it all wrapped up!

## Goals

- **Data Retrieval**: Gather match odds data for the 2023-2024 English Premier League season.
- **Data Cleaning**: Ensure data accuracy and consistency through pre-processing.
- **Data Analysis**:
  - Calculate potential returns for a specified stake on:
    - Home win
    - Draw
    - Away win
    - Favorite
    - Underdog
- **Random Selections**: Generate five sets of random match outcome selections (home win, draw, away win) for every game of the season.

## Setup

### Running the Notebook Locally with Jupyter Lab

1. **Install Jupyter Lab**:
   - Open your command line (Terminal on macOS/Linux or Command Prompt on Windows).
   - Install Jupyter Lab using pip:
     ```bash
     pip install jupyterlab
     ```

2. **Download the Project**:
   - Download the project files from the repository. You can download it as a ZIP file from GitHub and extract it to your desired directory.
   - Alternatively, you can clone the repository using Git:
     ```bash
     git clone https://github.com/your-username/epl-odds-analysis.git
     cd epl-odds-analysis
     ```

3. **Start Jupyter Lab**:
   - Navigate to the project directory in your command line:
     ```bash
     cd path/to/your/project/directory
     ```
   - Start Jupyter Lab:
     ```bash
     jupyter lab
     ```

4. **Open Jupyter Lab**:
   - Your default web browser will open Jupyter Lab, typically at http://localhost:8888/lab.

5. **Upload Files (if necessary)**:
   - In the Jupyter Lab interface, you can upload files by clicking the "Upload" button in the file browser pane on the left. Select the files you need from your local machine.

6. **Open the Notebook**:
   - In the Jupyter Lab interface, navigate to the project directory.
   - Open the `odds_english_premiership_gh.ipynb` notebook file.

### Running the Notebook Online with Google Colab

1. **Open Google Colab**:
   - Go to [Google Colab](https://colab.research.google.com/).

2. **Upload the Notebook**:
   - Click on File > Upload notebook and select the `odds_english_premiership_gh.ipynb` file you downloaded.

## Running the Project

Once you have chosen your environment (Jupyter Lab or Google Colab) and set it up, run the notebook by executing the cells to perform the data analysis and calculate potential returns for the specified betting strategies. I recommend running the notebook cell by cell to see the project unfold and understand each step of the analysis.

## Challenges

### Data retrieval from Websites Using JavaScript

#### Explanation

Some websites use JavaScript (not Java) to dynamically load content after the initial HTML is loaded. When you make a request using libraries like `requests`, you might not receive complete data because additional content is fetched or manipulated by JavaScript after the page loads.

#### Example Scenario

When visiting such a website, your browser fetches the initial HTML, and JavaScript running in the browser may subsequently make additional requests to fetch or update data based on user interactions or other triggers.

#### Challenges

- **Incomplete Data**: `requests` alone may not fetch dynamically loaded data, resulting in incomplete HTML content or placeholders.
- **Data Manipulation**: JavaScript can manipulate or fetch data after the initial page load, affecting data availability through basic HTTP requests.

#### Solutions

To handle websites using JavaScript for dynamic data loading, consider the following approaches:

- **Selenium Automation**: Automate interactions with the webpage using Selenium, which can execute JavaScript and retrieve dynamically loaded content.
- **API Inspection**: Identify API endpoints that JavaScript uses to fetch data by inspecting network requests in browser developer tools.
- **Direct API Requests**: Make direct requests to identified API endpoints using libraries like `requests` to fetch required data.
- **Using a Specific Endpoint**: Some websites provide specific URLs (endpoints) delivering structured data like JSON or XML, without needing to parse HTML. These endpoints are designed for programmatic access and can be discovered through website documentation or network inspection.

#### Initial Challenges

The initial challenge faced when attempting to fetch data from the oddsportal.com website directly using a web scraper or request was that retrieving HTML through `requests` and analyzing it using BeautifulSoup did not return the desired data. Further investigation revealed that the required data was brought into the site via an external endpoint.

### Finding the API Endpoint

1. **Visit the Website**: Navigate to the oddsportal.com website for Premier League 2023-2024 results.
2. **Using Browser Developer Tools**:
   - **Network Tab**: Navigate to the network tab to inspect network requests.
   - **Clear Log and Refresh**: Clear the network log, refresh the page, and observe requests made to load data.
   - **Identify the Endpoint**: Look for XHR requests (XMLHttpRequests) or other network requests fetching data dynamically.

### Capturing and Using the Endpoint

Steps to capture the endpoint using cURL and integrate it into your project:

1. **Capture with cURL**:
   - Right-Click on Request: Right-click on the identified API request in the browser's network tab.
   - Copy as cURL (bash): Select "Copy as cURL (bash)" to capture the request as a cURL command.

2. **Convert to Python Requests**:
   - Using cURL Converter: Paste the cURL command into a cURL to Python requests converter tool.
   - Generate Python Code: Convert the cURL command to Python requests code, including headers and parameters.

3. **Integrate into Your Project**:
   - Paste into Project: Insert the generated Python requests code snippet into your project.
   - Adjust Headers and Parameters: Customize headers, parameters, or other settings for a successful request.
   - Execute the Request: Execute the request within your project to fetch required data from the oddsportal.com API.

## Acknowledgments

Special thanks to all resources that facilitated the gathering and processing of data for this project.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
