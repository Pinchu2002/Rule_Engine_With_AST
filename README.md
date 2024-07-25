
# Rule Engine Evaluation

This project is a simple web application that evaluates rules based on user input. The rules are defined in the `rule_engine.py` file, and the web interface is provided by a Flask application.

## Project Structure
```bash
RULE_ENGINE_WITH_AST/
├── app.py
├── templates/
│   └── index.html
└── static/
    └── styles.css
```
## Prerequisites

Ensure you have Python 3.7 or higher installed on your system.

## Installation

1. Clone the repository or download the source code.

2. Create a virtual environment and activate it:

    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:

    ```bash
    pip install flask
    ```

## Running the Application

1. Initialize the database:
    python -c "from rule_engine import init_db; init_db()"

2. Run the Flask application:
    python app.py


3. Open your web browser and navigate to `http://127.0.0.1:5000` to access the application.

## Project Files

### index.html

This file contains the HTML form for user input and displays the evaluation result.

### app.py

This file contains the Flask application code that handles the web interface and interacts with the rule engine.

### rule_engine.py

This file contains the backend logic for creating, combining, and evaluating rules, as well as interacting with the SQLite database.
