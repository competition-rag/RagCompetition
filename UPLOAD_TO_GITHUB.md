# GitHub + Baidu Netdisk Upload Guide

## Repository Strategy
- GitHub stores code, documentation, and lightweight config templates.
- Baidu Netdisk stores the full runnable package.

## Recommended Split
Upload to GitHub:
- `rag_paper_search/`
- `app.py`
- `streamlit_app.py`
- `requirements.txt`
- `environment.yml`
- `README.md`
- `UPLOAD_TO_GITHUB.md`
- `BAIDU_NETDISK_TEMPLATE.md`
- `app_settings.example.json`
- `query_rewrite_rules.json`
- `scripts/`

Keep out of GitHub and place in Baidu Netdisk:
- `model/`
- `model_2w/`
- `taxonomy_tree/`
- `taxonomy_tree_test/`
- `cache/`
- `logs/`
- large CSV datasets
- benchmark outputs

## Local Config
1. Copy `app_settings.example.json` to `app_settings.json`
2. Fill in your `Qwen` and `OpenAlex` keys
3. Set `csv_path`, `taxonomy_tree_dir`, and `default_model_dir`

## Install
```bash
pip install -r requirements.txt
```

Or:
```bash
conda env create -f environment.yml
conda activate rag-paper-search
```

## Run
```bash
python -m streamlit run app.py
```

## Baidu Netdisk
- Full package link: `TO_BE_FILLED`
- Suggested archive name: `RAG_full_package.zip`

## GitHub Push
```bash
git add .
git commit -m "Prepare GitHub release with Baidu Netdisk distribution"
git push
```

## Security
- Do not upload `app_settings.json`
- Do not upload real API keys
- Do not upload large local artifacts unless you intentionally use external storage

