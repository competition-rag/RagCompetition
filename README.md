# RAG Intelligent Paper Search

An academic paper search UI with query understanding, taxonomy routing, BM25 retrieval, OpenAlex expansion, and Qwen summarization.

## Features
- Qwen query parsing
- Taxonomy-tree routing
- Local CSV + BM25 retrieval
- OpenAlex expansion
- Cross-encoder reranking
- Streamlit UI

## Quick Start
1. Copy `app_settings.example.json` to `app_settings.json`
2. Fill in API keys and local paths
3. Install dependencies
4. Run:

```bash
python -m streamlit run app.py
```

## Install
```bash
pip install -r requirements.txt
```

## Conda
```bash
conda env create -f environment.yml
conda activate rag-paper-search
```

## Important Files
- `app.py`: Streamlit entry
- `app_settings.json`: local config
- `model/`: classifier model
- `taxonomy_tree/`: routed CSV shards
- `query_rewrite_rules.json`: local query expansion rules

## Upload Notes
- Keep secrets out of GitHub
- Use Git LFS for large CSV/model files if you really need them in the repo
- See `UPLOAD_TO_GITHUB.md`

