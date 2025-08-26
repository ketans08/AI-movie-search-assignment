

## **Author**: Ketan Sahu (221010223, ECE)

# Movie Semantic Search Assignment


This repository contains my solution for the semantic search on movie plots assignment using `SentenceTransformers` (model: `all-MiniLM-L6-v2`). It loads a small dataset, builds embeddings, and performs cosine-similarity based retrieval via `search_movies(query, top_n)`.

## What I Did
- Implemented semantic search in `movie_search.py` using `all-MiniLM-L6-v2`
- Encoded plots to embeddings and used cosine similarity (scaled to 0..1)
- Added a simple CLI to run queries from terminal (`--query`, `--top-n`)
- Wrote unit tests (`tests/test_movie_search.py`) to validate output shape, count, range, relevance
- Prepared a minimal dataset `movies.csv` (title, plot) for quick verification
- Documented setup, usage, and troubleshooting in this README

## Repository Structure
- `movie_search.py`: Module implementing semantic search
- `movies.csv`: Tiny sample dataset (title, plot)
- `tests/test_movie_search.py`: Unit tests for `search_movies`
- `requirements.txt`: Project dependencies
- `README.md`: This file

## Prerequisites
- Python 3.9+
- Git

## Clone the Repository
```bash
git clone https://github.com/your-username/movie-search-assignment.git
cd movie-search-assignment
```

## Create and Activate Virtual Environment
Choose the command that matches your shell/OS.

- Bash/Zsh (Linux/macOS):
```bash
python -m venv venv
source venv/bin/activate
```

- Windows (PowerShell):
```powershell
python -m venv venv
venv\Scripts\Activate.ps1
```

## Install Dependencies
```bash
pip install -r requirements.txt
```

## How to Run
Run a query directly from the terminal using the CLI:
```bash
python movie_search.py --query "spy thriller in Paris" --top-n 3
```
This prints a concise table with `title` and `similarity`.

## Run Unit Tests
```bash
python -m unittest tests/test_movie_search.py -v
```

## Notes
- Model used: `sentence-transformers/all-MiniLM-L6-v2`
- Similarity metric: cosine similarity (scaled to 0..1)

## Example
```bash
python movie_search.py --query "spy thriller in Paris" --top-n 2
```
Expected: `Spy Movie` ranks at the top.

## Troubleshooting
- First run downloads the model; ensure internet access.
- If activation fails, run with your venv Python directly:
```bash
./venv/bin/python movie_search.py --query "spy thriller in Paris" --top-n 3
```
