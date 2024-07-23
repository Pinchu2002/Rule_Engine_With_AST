
# Rule Engine with AST

## Objective
Develop a simple 3-tier rule engine application to determine user eligibility based on attributes like age, department, income, spend, etc. The system uses Abstract Syntax Tree (AST) to represent conditional rules and allows for dynamic creation, combination, and modification of these rules.

## Data Structure
- **Node**: Represents each element of the AST with fields:
  - `type`: String indicating the node type ("operator" for AND/OR, "operand" for conditions).
  - `left`: Reference to another Node (left child).
  - `right`: Reference to another Node (right child for operators).
  - `value`: Optional value for operand nodes (e.g., number for comparisons).

## Data Storage
- SQLite database to store rules and application metadata.
- Schema:
  ```sql
  CREATE TABLE IF NOT EXISTS rules (
      id INTEGER PRIMARY KEY,
      rule_text TEXT
  );
  ```

## API Functions
1. **create_rule(rule_string)**: Takes a string representing a rule and returns a Node object representing the corresponding AST.
2. **combine_rules(rules)**: Takes a list of rule strings and combines them into a single AST. Returns the root node of the combined AST.
3. **evaluate_rule(node, data)**: Takes a JSON representing the combined rule's AST and a dictionary data containing attributes. Evaluates the rule against the provided data and returns `True` if the user matches the rule, `False` otherwise.

## Usage

### Initialize Database
```python
init_db()
```

### Save Rule
```python
save_rule(rule1)
```

### Create Rule
```python
node = create_rule(rule1)
```

### Combine Rules
```python
combined_node = combine_rules([rule1, rule2])
```

### Evaluate Rule
```python
data = {"age": 35, "department": "Sales", "salary": 60000, "experience": 3}
result = evaluate_rule(combined_node, data)
print(result)  # Should print True or False based on the evaluation
```

## Test Cases
1. Create individual rules from the examples using `create_rule` and verify their AST representation.
2. Combine the example rules using `combine_rules` and ensure the resulting AST reflects the combined logic.
3. Implement sample JSON data and test `evaluate_rule` for different scenarios.

## Dependencies
- Python 3.6+
- SQLite

## Setup
1. Clone the repository.
2. Install dependencies: `pip install -r requirements.txt`.
3. Run the script: `python rule_engine.py`.

## Design Choices
- Used AST for efficient and flexible rule representation.
- SQLite for lightweight and easy-to-use data storage.
- Modular design for easy extension and maintenance.

## Additional Features (Bonus)
- Error handling for invalid rule strings or data formats.
- Validation for attributes to be part of a catalog.
- Modification of existing rules.
- Support for user-defined functions within the rule language for advanced conditions.
