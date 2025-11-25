### Text-to-SQL Assistant

### Overview 

Text-to-SQL Assistant is a mini LLM project where I fine-tuned the Qwen 1.5B model using LoRA to convert plain English questions into valid SQL queries.

It lets non-technical users interact with a database simply by typing questions like:
“Show me the top 5 customers by total purchase amount” --> Generates SQL automatically

The project uses the Gretel Synthetic Text-to-SQL dataset and includes full training, evaluation, and inference workflows.


### Tech Stack 

Model: Qwen-1.5B
Fine-tuning: LoRA 
Training Framework: HuggingFace Transformers + PEFT
Dataset: gretelai/synthetic_text_to_sql
Runtime: Python, Google colab
Hardware: T4 GPU

### Training & Evaluation 

1. Baseline accuracy before fine-tune: low
2. After LoRA fine-tuning: significant improvement in structure & correctness
3. Model produces cleaner SELECT, WHERE, ORDER BY clauses
4. Able to handle multi-condition queries and aggregation

### Example Output 

Input: 
“List all employees hired after 2020 who work in the Finance department.”

Output SQL:
SELECT name, hire_date, department
FROM employees
WHERE hire_date > '2020-01-01'
  AND department = 'Finance';

  