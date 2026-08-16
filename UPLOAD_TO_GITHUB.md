# GitHub 上传与发布说明

本文档用于说明本项目在 GitHub 与百度网盘之间的分发方式，以及提交、打包和发布时的推荐操作。

## 一、发布策略

由于本项目包含模型权重、学科树分片、大规模论文 CSV 数据、BM25 缓存等大体积资源，因此采用“双通道分发”方式：

- GitHub：存放源码、文档、脚本、配置模板和轻量示例
- 百度网盘：存放完整可运行资源包

这样既能保证仓库整洁、便于展示与协作，也能保证评审或使用者可以下载完整版本进行复现。

## 二、推荐上传到 GitHub 的内容

建议上传以下内容到 GitHub：

- `rag_paper_search/`
- `scripts/`
- `benchmarks/`
- `docs/`
- `app.py`
- `requirements.txt`
- `environment.yml`
- `README.md`
- `UPLOAD_TO_GITHUB.md`
- `BAIDU_NETDISK_TEMPLATE.md`
- `app_settings.example.json`
- 规则配置文件
- 轻量测试数据或示例文件

## 三、不建议上传到 GitHub 的内容

以下内容建议放入百度网盘完整包，而不要直接上传到 GitHub：

- `model/`
- 大型分类模型权重文件
- `taxonomy_tree/`
- `cache/`
- `logs/`
- 大规模 CSV 论文库
- 本地评测输出的大文件
- 临时缓存文件
- 含有真实 API 密钥的配置文件

## 四、配置文件处理建议

请保留一个公开模板配置文件：

- `app_settings.example.json`

本地实际运行配置建议使用：

- `app_settings.json`

注意事项：

- `app_settings.json` 不要上传到 GitHub
- 不要在仓库中泄露真实 API Key
- 建议在模板文件中只保留字段结构与示例值

## 五、推荐的仓库结构

```text
RAG智能论文搜索系统/
├─ app.py
├─ README.md
├─ requirements.txt
├─ environment.yml
├─ app_settings.example.json
├─ UPLOAD_TO_GITHUB.md
├─ BAIDU_NETDISK_TEMPLATE.md
├─ rag_paper_search/
├─ scripts/
├─ benchmarks/
└─ docs/
```

## 六、完整资源包建议包含的内容

百度网盘完整包建议包含：

- 源码
- `model/`
- `taxonomy_tree/`
- 必要的论文 CSV 数据
- 可选 BM25 缓存
- 示例配置文件
- 项目说明文档

推荐压缩包命名：

- `RAG_full_package.zip`

## 七、首次使用者的运行流程

1. 克隆或下载 GitHub 仓库
2. 从百度网盘下载完整资源包
3. 将模型、数据、学科树等资源放入指定目录
4. 将 `app_settings.example.json` 复制为 `app_settings.json`
5. 填写 API 与本地路径配置
6. 安装依赖
7. 启动 Streamlit

```bash
python -m streamlit run app.py
```

## 八、依赖安装

### pip

```bash
pip install -r requirements.txt
```

### conda

```bash
conda env create -f environment.yml
conda activate rag-paper-search
```

## 九、上传前检查清单

在推送 GitHub 前，建议逐项检查：

- 是否删除了本地缓存和日志大文件
- 是否移除了真实 API 密钥
- 是否确认 `README.md` 与当前项目一致
- 是否确认百度网盘链接可访问
- 是否保留了配置模板文件
- 是否补充了运行说明和依赖说明

## 十、推荐的发布说明

在 GitHub 仓库首页建议说明以下内容：

- 项目目标与应用场景
- 系统核心模块
- GitHub 与百度网盘的分工
- 安装和启动方法
- 资源下载方式
- 注意事项

## 十一、推送 GitHub 的基本流程

```bash
git add .
git commit -m "Prepare release version for GitHub distribution"
git push
```

## 十二、安全与合规建议

- 不上传真实密钥
- 不上传隐私数据
- 不上传未授权分发的数据资源
- 明确标注外部模型、API、数据与参考工作的来源

## 十三、比赛提交建议

若本项目用于比赛提交，建议：

- GitHub 作为源码展示仓库
- 百度网盘作为完整运行资源下载方式
- 项目文档、作品简介、视频和其他材料中的项目描述保持一致
- 所有效果指标、资源来源、技术引用均做到可解释、可追溯
