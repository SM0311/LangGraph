# LangGraph Workflows

This repository contains Jupyter notebooks and code examples demonstrating the use of [LangGraph](https://github.com/langchain-ai/langgraph) and [LangChain](https://github.com/langchain-ai/langchain) for workflow automation, prompt chaining, and parallel/sequential graph execution in Python.

## Contents
- `2_simple_llm_workflow.ipynb`: Simple LLM Q&A workflow using LangGraph and LangChain OpenAI.
- `3_propmt_chaining.ipynb`: Blog generation workflow with prompt chaining (title → outline → content → evaluation).
- `batsman_workflow.ipynb`: Parallel workflow for cricket batsman statistics, demonstrating reducer usage for parallel state updates.
- `requirements.txt`: Python dependencies for running the notebooks.

## Setup
1. **Clone the repository:**
   ```sh
   git clone https://github.com/SM0311/LangGraph.git
   cd LangGraph
   ```
2. **Create a virtual environment:**
   ```sh
   python -m venv myenv
   myenv\Scripts\activate  # On Windows
   ```
3. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```
4. **Configure API keys:**
   - Create a `.env` file (not included in the repo) with your OpenAI API key:
     ```
     OPENAI_API_KEY=your-key-here
     ```

## Usage
- Open any notebook in Jupyter or VS Code and run the cells.
- Make sure your `.env` file is present and contains valid API keys.

## Security
- `.env` and `myenv/` are excluded from version control via `.gitignore`.
- **Do not commit API keys or secrets.**

## License
This project is for educational purposes. See individual libraries for their licenses.

---
**Author:** Suraj Mishra
