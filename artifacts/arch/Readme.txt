README.txt
===========

Anomaly Detection and Automated Task Creation with LLM and Isolation Forest
-------------------------------------------------------------------------------

This Python project automates anomaly detection in financial data, leveraging Machine Learning (Isolation Forest), LLM-enhanced explanations (via OpenAI), JIRA ticket creation, Agentic AI task generation, and email reporting.

--------------------------------------------------------------------------------
1. PREREQUISITES
--------------------------------------------------------------------------------

Make sure you have Python 3.8 or higher installed.

Install the following Python packages before running the script:

- pandas
- numpy
- scikit-learn
- smtplib (standard library)
- email (standard library)
- logging (standard library)
- requests
- openai
- jira

You can install the necessary external packages using pip:



--------------------------------------------------------------------------------
2. CONFIGURATION
--------------------------------------------------------------------------------

Before running the script, update the following configurations in the code:

 -----------------------------------**OpenAI API Key**---------------------------------------------
openai.api_key = "your-openai-api-key"

---------------------------------------------Jira Configuration---------------------------------------------
jira_url = "https://your-domain.atlassian.net" jira_user = "your-email@example.com" jira_token = "your-jira-api-token"

Replace `YOUR_PROJECT_KEY` in the `create_jira_ticket()` function with your actual JIRA project key.


---------------------------------------------**Agentic AI API Key**---------------------------------------------

AGENTIC_API_KEY = "your-agentic-api-key"


---------------------------------------------**Email Configuration**---------------------------------------------
- Sender email and app password (recommended: use an app password if using Gmail)


- Recipient email (in `send_email_tool` function call)

send_email_tool(df[df['Anomaly'] == 1], "recipient@example.com", le_account, le_au, le_company)


---------------------------------------------**Input File Paths**---------------------------------------------
file_path = "/path/to/your/file.csv" feedback_file_path = "/path/to/your/feedback_file.csv"


- Provide the correct paths to your input dataset and feedback dataset CSV files.

--------------------------------------------------------------------------------
3. INPUT FILES FORMAT
--------------------------------------------------------------------------------

---------------------------------------------**Primary Data File**---------------------------------------------
- Must contain the following columns:
  - `Asofdate`
  - `Company`
  - `Account`
  - `AU`
  - `Match Status`
  - `GL Balance`
  - `IHub balance`
  - `Balance difference`

---------------------------------------------**Feedback Data File** (`feedback_file.csv`)---------------------------------------------
- Should contain at least:
  - A `feedback` column (binary values: 1 for true anomaly, 0 for false positive)

--------------------------------------------------------------------------------
4. HOW TO RUN
--------------------------------------------------------------------------------

You can run the script from the terminal or an IDE by executing the `main()` function with the correct file paths.

Example:
```python
file_path = "/absolute/path/to/your/file.csv"
feedback_file_path = "/absolute/path/to/your/feedback_file.csv"

main(file_path, feedback_file_path)


And then run the script from your terminal:
python your_script.py


