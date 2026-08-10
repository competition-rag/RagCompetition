# RAG Intelligent Paper Search

Academic paper search UI with query understanding, taxonomy routing, BM25 retrieval, OpenAlex expansion, and Qwen summarization.

## Distribution Mode
- GitHub: source code and documentation
- Baidu Netdisk: (https://pan.baidu.com/s/1mFMTfZzLwxhHCCF0Jmo5uA?pwd=x1uw)

## Features
- Qwen query parsing
- Taxonomy-tree routing
- Local CSV + BM25 retrieval
- OpenAlex expansion
- Cross-encoder reranking
- Streamlit UI

## Quick Start
1. Download the full package from Baidu Netdisk
2. Copy `app_settings.example.json` to `app_settings.json`
3. Fill in API keys and local paths
4. Install dependencies
5. Run:

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

## Download
- Baidu Netdisk full package: `TO_BE_FILLED`
- Suggested package name: `RAG_full_package.zip`

## Important Files
- `app.py`: Streamlit entry
- `app_settings.example.json`: public config template
- `UPLOAD_TO_GITHUB.md`: upload and distribution guide
- `BAIDU_NETDISK_TEMPLATE.md`: placeholder text for your Netdisk link

## Notes
- Keep secrets out of GitHub
- Keep large datasets and model files out of GitHub
- Use Baidu Netdisk for the full project assets

