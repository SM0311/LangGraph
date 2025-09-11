# LangGraph Workflows

This repository contains Jupyter notebooks and code examples demonstrating the use of [LangGraph](https://github.com/langchain-ai/langgraph) and [LangChain](https://github.com/langchain-ai/langchain) for workflow automation, prompt chaining, and parallel/sequential graph execution in Python.

## Contents

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

## Security

## License
This project is for educational purposes. See individual libraries for their licenses.

**Author:** Suraj Mishra


# Welcome to the LangGraph Workflow Playground!

This repository is your hands-on guide to mastering LangGraph for building smart, persistent, and flexible workflows in Python. Whether you're a beginner or an advanced user, you'll find everything you need to understand, experiment, and extend workflow automation using Jupyter notebooks.

---

## What is LangGraph?
LangGraph is a Python library that lets you build workflows as graphs, where each node can be a function, a prompt, or any logic you want. It supports state management, persistence, and parallel execution, making it perfect for real-world automation, data science, and AI projects.

---

## 📚 Notebooks: Your Learning Journey

Each notebook in this repo is a step-by-step story. Here’s what you’ll find:

- **0_test_installation.ipynb**
   - *Purpose*: Make sure your environment is set up and LangGraph is installed correctly.
   - *What to do*: Run all cells. If you see no errors, you’re good to go!

- **1_BMI_workflow.ipynb**
   - *Purpose*: Learn how to build a simple workflow for calculating BMI (Body Mass Index).
   - *Key Concepts*: State definition, node creation, graph compilation, and basic invocation.
   - *Try it*: Change the input values and see how the workflow responds.

- **2_simple_llm_workflow.ipynb**
   - *Purpose*: See how to use LangGraph with a language model (LLM) for Q&A or text generation.
   - *Key Concepts*: Integrating LLMs, prompt chaining, and state updates.
   - *Try it*: Ask different questions and watch the workflow generate answers.

- **3_propmt_chaining.ipynb**
   - *Purpose*: Explore how to chain multiple prompts and nodes to create a blog post generator.
   - *Key Concepts*: Sequential node execution, passing state between nodes, and evaluation.
   - *Try it*: Tweak the prompts or add new steps to customize your workflow.

- **batsman_workflow.ipynb**
   - *Purpose*: Dive into parallel workflows using cricket batsman statistics as an example.
   - *Key Concepts*: Parallel node execution, reducers, and merging state updates.
   - *Try it*: Add more batsmen or stats to see how parallelism works.

- **10_persistence.ipynb**
   - *Purpose*: Master advanced features like persistence, state history, time travel, and multi-threaded workflows.
   - *Key Concepts*: Checkpointing, restoring state, updating state at any point, and running multiple threads (sessions).
   - *Try it*: Experiment with updating state at a checkpoint, invoking from that point, and exploring the state history.

---

## 🧠 Key Concepts Explained (In Plain English)

### Persistence
Imagine you’re playing a video game and you can save your progress at any point. LangGraph lets you do the same with workflows! You can checkpoint the state, come back later, and pick up right where you left off. This is great for long-running tasks, experiments, or debugging.

### State History
Every time your workflow changes, LangGraph keeps a log. You can look back and see every step, every change, and every result. This is super useful for understanding what happened, finding bugs, or just being curious.

### Time Travel
Ever wish you could go back and change something? With LangGraph, you can! Update the state at any checkpoint, then re-run the workflow from that point. It’s like rewinding and rewriting history.

### Threads (Sessions)
You can run multiple workflows in parallel, each with its own state and history. Think of threads as separate workspaces—great for handling multiple users, tasks, or experiments at once.

---

## 🛠️ How to Use This Repo

1. **Clone the repository**
    ```sh
    git clone https://github.com/SM0311/LangGraph.git
    cd LangGraph
    ```
2. **Set up your environment**
    - Create a virtual environment:
       ```sh
       python -m venv myenv
       myenv\Scripts\activate  # On Windows
       ```
    - Install dependencies:
       ```sh
       pip install -r requirements.txt
       ```
    - Add your API keys to a `.env` file (see notebooks for details).
3. **Open the notebooks** in Jupyter or VS Code and start running cells!

---

## 🔍 Practical Examples

### Persistence & Time Travel
```python
# Save your workflow state at a checkpoint
workflow.update_state({'configurable':{'thread_id':'1','checkpoint_id':"<checkpoint_id>"}},{'topic':'samosa'})

# Re-run the workflow from that checkpoint
result = workflow.invoke(None, {'configurable': {'thread_id': '1', 'checkpoint_id': '<checkpoint_id>'}})
print(result)
```

### State History
```python
# See every step your workflow took
history = list(workflow.get_state_history({'configurable':{'thread_id':'1'}}))
for state in history:
      print(state)
```

### Multi-Threaded Workflows
```python
# Run two workflows at the same time
config1 = {'configurable':{'thread_id':'1'}}
config2 = {'configurable':{'thread_id':'2'}}
workflow.invoke({'topic':'pizza'}, config=config1)
workflow.invoke({'topic':'pasta'}, config=config2)
```

---

## 💡 Tips & Best Practices

- Always invoke from the checkpoint you updated to see your changes.
- Use thread IDs to keep your workflows organized and independent.
- Check state history to debug, audit, or just understand your workflow’s journey.
- Don’t be afraid to experiment—LangGraph is designed for exploration!

---

## ⚙️ Requirements

- Python 3.8 or newer
- LangGraph
- Jupyter Notebook
- Other dependencies listed in `requirements.txt`

---

## 👋 Final Thoughts

This repo is meant to be your playground and reference for everything LangGraph. Every notebook is a lesson, every cell is an experiment. If you ever get stuck, just read through the comments, check the state history, or try time traveling in your workflow!

If you have questions, want to contribute, or just want to say hi, feel free to reach out or open an issue.

Happy workflow building! 🚀
