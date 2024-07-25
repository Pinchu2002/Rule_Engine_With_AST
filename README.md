# Rule Engine Evaluation

## Overview

This project is a Flask-based web application designed to evaluate rules based on user input. The rules are stored in a SQLite database, and the evaluation results are saved for future reference. The application provides a user-friendly interface for inputting data and displays the evaluation results based on predefined rules.

## Project Structure
```bash
RULE_ENGINE_WITH_AST/
├── app.py
├── rule_engine.py
├── templates/
│   └── index.html
└── static/
    └── styles.css
```
## Prerequisites

Ensure you have Python 3.7 or higher installed on your system.

## Installation

### Clone the Repository

First, clone the repository to your local machine:

```bash
git clone https://github.com/yourusername/rule-engine-evaluation.git
cd rule-engine-evaluation
```
## Create a Virtual Environment

Create a virtual environment to manage dependencies:

```bash
python3 -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```
## Install Dependencies

Install the necessary dependencies using pip:
```bash
pip install -r requirements.txt
```

## Initialize the Database

Initialize the SQLite database by running the Flask application:
```bash
python app.py
```
This will create the SQLite database and necessary tables.

## Usage

To use the application:
- Run the Application
```bash
   python app.py
```
- Open your browser and navigate to http://127.0.0.1:5000/
- Fill in the form with the required information and click "Evaluate" to see the result.


## Files Description
### app.py

This is the main Flask application file. It defines the routes, handles form submissions, and integrates the rule engine.
- index: Renders the main page with the form.
- evaluate: Handles form submissions, evaluates the rules based on input, and displays the result.

### rule_engine.py

This file contains the logic for the rule engine, including functions to create, combine, evaluate rules, and interact with the SQLite database.
- init_db: Initializes the SQLite database and creates the necessary tables.
- save_rule: Saves a rule to the database.
- save_evaluation_result: Saves the evaluation result to the database.
- create_rule: Converts a rule string into an AST node.
- combine_rules: Combines multiple rules using logical operators.
- evaluate_rule: Evaluates the combined rule against the provided data.

### templates/index.html

The HTML template for the web application. It includes the form for user input and displays the evaluation result.