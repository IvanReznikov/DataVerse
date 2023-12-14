# DataVerse
)
Welcome to DataVerse, a repository dedicated to sharing code snippets and notebooks used in my blog posts, articles, and conference talks on machine learning, data science, and related topics.

## Contents

This repository contains a collection of code snippets, notebooks, my Langchain 101 Course and other materials.

## Usage

Feel free to use the code in this repository for your own projects, or to learn from it. Kindly give credit to DataVerse and link back to the original post or article where the code was used.

## License

All code in this repository is licensed under the MIT License. This means that you are free to use, modify, and distribute the code as long as you give credit to DataVerse and include the original license in your work.

## Contact

If you have any questions or comments about this repository, please feel free to reach out to us at [ivanreznikov@gmail.com](mailto:ivanreznikov@gmail.com).

## Code Environment Setup

I provide a Docker image for this course that uses [Jupyter Notebooks](https://jupyter.org/). Docker allows you to run the class's code in an environment precisely matching the one in which the code was developed and tested. You can also use the Docker image to run the course code in VSCode or another editor (see below).

In addition to Docker you can also setup an environment locally using the instructions below.

### Install Docker

[Install docker](https://docs.docker.com/engine/install/) and then check the [Get Started](https://www.docker.com/get-started/) page if you aren't familiar.

There are several docker containers used in this course:

- `jupyter`: Jupyter Notebook server where we will interactively write and run code.
- `chroma`: Chroma vector database server where we will store and query vector embeddings of documents for RAG.
- `neo4j`: Neo4j graph database server where we will store and query graph data for prompt engineering and fine-tuning LLMs.
- `opensearch`: OpenSearch server where we will store and query documents for RAG.

### Docker Compose

Bring up the course environment with the following command:

```bash
docker compose up -d
```

Find the Jupyter Notebook url via this command:

```bash
docker logs jupyter -f --tail 100
```

Look for the url with `127.0.0.1` and open it. You should see the Jupyter Notebook home page.

NOTE: Insert an image of Jupyter home page for this course.

### Docker and VSCode

NOTE: add instructions.

## Code-Level Environment Setup

We use a Docker image to run the course, but you can also setup the environment so the code will work in VSCode or another editor. We provide a development tools setup using `black`, `flake8`, `isort`, `mypy` and `pre-commit` for you to modify and use as you see fit.

### Install Anaconda Python

We use Anaconda Python, Python version 3.10.0, for this course. You can download Anaconda Python from [here](https://www.anaconda.com/products/individual). Once you have installed Anaconda Python, you can create a new environment for this course by running the following command:

```bash
conda create -n chatbot-class python=3.10 -y
```

When you create a new environment or start a new shell, you will need to activate the `chatbot-class` conda environment with the following command:

```bash
conda activate chatbot-class
```

Now you are running Python 3.10 in the `chatbot-class` environment. To use this Python in VSCode, hit SHIFT-CMD-P (on Mac) and select `Python: Select Interpreter`. Then select the `chatbot-class` environment's Python.

To deactivate this environment, run:

```bash
conda deactivate
```

#### Other Virtual Environments

Note: I don't support other environments, but you can actually use any Python 3.10 if you are smart enough to make that work. :) You will need to manage your own virtual environments. Python 3's [`venv`](https://docs.python.org/3/library/venv.html) are easy to use.

To create a `venv` for the project, run:

```bash
python3 -m venv chatbot-class
```

To activate this venv run:

```bash
source chatbot-class/bin/activate
```

To deactivate this environment, run:

```bash
deactivate
```

### Install Poetry for Dependency Management

We use [Poetry](https://python-poetry.org/) for dependency management, as it makes things fairly painless. 

Verify [Poetry installation instructions here](https://python-poetry.org/docs/#installation) so you know the URL `https://install.python-poetry.org` is legitimate to execute in `python3`.

Then install Poetry with the following command:

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

It is less "clean" in terms of environmental isolation, but alternatively you can install poetry via `pip`:

```bash
pip install poetry
```

### Install Dependencies via Poetry

```bash
poetry install
```

## Essential Tools

### [`langchain`](https://www.langchain.com/) ([docs](https://python.langchain.com/docs/get_started/introduction))

> LangChain is a framework for developing applications powered by language models. It enables applications that:
>
> * Are context-aware: connect a language model to sources of context (prompt instructions, few shot examples, content to ground its response in, etc.)
> * Reason: rely on a language model to reason (about how to answer based on provided context, what actions to take, etc.)
>
> The main value props of LangChain are:
>
> * Components: abstractions for working with language models, along with a collection of implementations for each abstraction. Components are modular and easy-to-use, whether you are using the rest of the LangChain framework or not
> * Off-the-shelf chains: a structured assembly of components for accomplishing specific higher-level tasks
Off-the-shelf chains make it easy to get started. For complex applications, components make it easy to customize existing chains and build new ones.

### [`langchain-hub`](https://github.com/hwchase17/langchain-hub)

> Taking inspiration from Hugging Face Hub, LangChainHub is collection of all artifacts useful for working with LangChain primitives such as prompts, chains and agents. The goal of this repository is to be a central resource for sharing and discovering high quality prompts, chains and agents that combine together to form complex LLM applications.

See [example usage here](https://python.langchain.com/docs/use_cases/question_answering/).

### [`llama-index`](https://github.com/jerryjliu/llama_index)

> LlamaIndex is a "data framework" to help you build LLM apps. It provides the following tools:
>
> * Offers data connectors to ingest your existing data sources and data formats (APIs, PDFs, docs, SQL, etc.)
> * Provides ways to structure your data (indices, graphs) so that this data can be easily used with LLMs.
> * Provides an advanced retrieval/query interface over your data: Feed in any LLM input prompt, get back retrieved context and knowledge-augmented output.
> * Allows easy integrations with your outer application framework (e.g. with LangChain, Flask, Docker, ChatGPT, anything else).
>
> LlamaIndex provides tools for both beginner users and advanced users. Our high-level API allows beginner users to use LlamaIndex to ingest and query their data in 5 lines of code. Our lower-level APIs allow advanced users to customize and extend any module (data connectors, indices, retrievers, query engines, reranking modules), to fit their needs.

