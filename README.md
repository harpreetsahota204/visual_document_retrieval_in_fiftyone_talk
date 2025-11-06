# Visual Document Retrieval in FiftyOne

**How to Cluster, Search and Uncover Insights in Document Image Datasets Using Embeddings**

Presentation by Harpreet Sahota, Hacker-in-Residence @ Voxel51

[![Open Slides](https://img.shields.io/badge/Google_Slides-FBBC04?style=for-the-badge&logo=google-slides&logoColor=white)](https://docs.google.com/presentation/d/1W2Rq9wgvsb6uFt3d1fR9hBe3W3WPnIWWlz8e7Lm5GSw/edit?usp=sharing)

## 📓 Resources

- **[Demo Notebook](vdr_talk_notebook.ipynb)** - Complete workflow using the Visual AI at NeurIPS 2025 dataset
- **[Slides](https://docs.google.com/presentation/d/1W2Rq9wgvsb6uFt3d1fR9hBe3W3WPnIWWlz8e7Lm5GSw/edit?usp=sharing)** - Full presentation deck

## What This Talk Covers

### The Problem
Why text-only search fails for documents:
- Documents are multimodal (text + tables + charts + diagrams + layout)
- OCR pipelines lose structure, visual elements become invisible
- Can't search for "papers with ablation tables" or "charts showing trends"

### The Solution  
Visual document retrieval models that:
- Process documents at high resolution (896-2048px vs CLIP's 224px)
- Understand spatial structure and layout
- Learn document-specific patterns (tables, charts, diagrams)
- Enable search by what documents *look like*, not just what they say

### The Toolkit
FiftyOne Brain capabilities for document understanding:
- **Compute embeddings** - Transform documents into searchable vectors
- **Visualize** - UMAP plots reveal natural research clusters
- **Compute uniqueness** - Find near-duplicates and novel papers
- **Compute similarity** - Search with text queries or example documents
- **Compute representativeness** - Identify prototypical vs outlier papers

### The Use Case
Live demo navigating 1,134 NeurIPS 2025 vision papers:
- Visualize research landscape and discover clusters
- Text search: "diffusion models for medical imaging"
- Visual similarity: Find papers with similar architecture diagrams
- Build personalized conference schedule in 45 minutes

## Quick Start

```bash
pip install fiftyone torch transformers pillow umap-learn
pip install git+https://github.com/illuin-tech/colpali.git@vbert#egg=colpali-engine
```

```python
import fiftyone as fo
from fiftyone.utils.huggingface import load_from_hub

# Load the NeurIPS dataset
dataset = load_from_hub("Voxel51/visual_ai_at_neurips2025")

# Follow the notebook for complete workflow
```

## Related Resources

- **FiftyOne Brain**: [docs.voxel51.com/brain.html](https://docs.voxel51.com/brain.html)
- **Visual AI at NeurIPS Dataset**: [huggingface.co/datasets/Voxel51/visual_ai_at_neurips2025](https://huggingface.co/datasets/Voxel51/visual_ai_at_neurips2025)
- **Voxel51 on Hugging Face**: [huggingface.co/Voxel51](https://huggingface.co/Voxel51)

## The Core Insight

Documents are visual artifacts. Visual document retrieval preserves the structure, layout, and visual elements that text extraction destroys - enabling search by semantic meaning AND visual patterns.
