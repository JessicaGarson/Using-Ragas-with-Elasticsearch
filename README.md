# Using Ragas with Elasticsearch
Ragas is a framework for evaluating RAG pipelines with human-aligned metrics. This repository contains a demo using a sample book dataset and Elasticsearch.

For more details, see the [Ragas GitHub](https://github.com/explodinggradients/ragas).

## Setting up
- The version of Python that is used is Python 3.12.1 but you can use any version of Python higher than 3.9.
- This demo uses Elasticsearch version 9.0.3, but you can use any version of Elasticsearch that is higher than 8.0.

## Stucture of the example
- **[books.json](books.json)**: The dataset used containing an sample of books.
- **[ragas-elasticsearch-demo.ipynb](ragas-elasticsearch-demo.ipynb)**: Main Jupyter notebook for running ragas evaluations. It sets up the environment, loads data, runs sample queries, and computes evaluation metrics (context precision, faithfulness, answer relevancy) using ragas.
- **[ragas_evaluation.csv](ragas_evaluation.csv)**: Output file generated by the notebook, containing detailed results for each evaluation query, including metrics for context precision, faithfulness, and answer relevancy.

## Usage

1. **Install Dependencies**
   The notebook will install required dependencies automatically, but you can also install them manually:
   
   ```bash
   pip install -q ragas datasets langchain elasticsearch openai langchain-openai
   ```

   You will also need an OpenAI API key for LLM-based metrics. You will want to configure an environment variable for your OpenAI API Key, which you can find on the API keys page in [OpenAI's developer portal](https://platform.openai.com/api-keys).

3. **Run the Notebook**
   Open `ragas-elasticsearch-demo.ipynb` in Jupyter and follow the instructions to run each cell. The notebook will:
   
   - Query your book index (via Elasticsearch)
   - Run sample RAG queries
   - Evaluate the responses using Ragas
   - Output results to `ragas_evaluation.csv`

5. **View Results**
   
   The results file contains detailed metrics for each test query. Use it to analyze the quality of your RAG pipeline and compare different configurations.
