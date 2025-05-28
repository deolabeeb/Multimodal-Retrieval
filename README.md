# Multimodal Retrieval System with CLIP & FAISS

## 🔍 Project Overview
Build a **Multimodal Retrieval System** that supports both **text-to-image** and **image-to-text** search using **OpenAI’s CLIP** model and **FAISS** for efficient similarity search. This system allows you to:

- Query images using text prompts ("a cat wearing sunglasses")
- Retrieve the most relevant captions for a given image
- Serve results through an interactive **Streamlit** app or a **FastAPI** endpoint

## 🧰 Tech Stack
- **PyTorch**
- **CLIP** via Hugging Face (`openai/clip-vit-base-patch32`)
- **FAISS** for Approximate Nearest Neighbor (ANN) search
- **Streamlit** or **FastAPI** for UI/API
- **Pillow**, **numpy**, **pandas**, **tqdm**, etc.

## 📁 Project Structure
```
multimodal-retrieval-clip-faiss/
├── app/                        # Streamlit/FastAPI app
├── data/                       # Images and captions
├── models/                     # CLIP model loader
├── index/                      # FAISS index handling
├── utils/                      # Preprocessing utils
├── notebooks/                  # EDA and experiments
├── requirements.txt
├── Dockerfile
└── README.md
```

## 📦 Installation
```bash
git clone https://github.com/yourusername/multimodal-retrieval-clip-faiss.git
cd multimodal-retrieval-clip-faiss
pip install -r requirements.txt
```

## 🚀 Usage
### 1. Prepare Dataset
Download and preprocess a subset of **MS-COCO**:

```bash
mkdir -p data/images data/captions
# Example download script (or link to dataset)
```

Example dataset download links:
- [MS COCO 2017 Images (train)](http://images.cocodataset.org/zips/train2017.zip)
- [MS COCO Captions](https://github.com/tylin/coco-caption)

### 2. Build FAISS Index
```bash
python scripts/build_faiss_index.py
```

### 3. Launch App
#### Option A: Streamlit
```bash
streamlit run app/streamlit_app.py
```

#### Option B: FastAPI
```bash
uvicorn app.fastapi_app:app --reload
```

## 📊 Example
- Input Text: "A dog in a birthday hat"
- Output: Top 5 matching images from dataset

## 🧪 Dataset
- **MS-COCO**: [https://cocodataset.org/#download](https://cocodataset.org/#download)
  - Use captions and images from the 2017 training set.
  - Format: Image file + associated text captions

Alternatives:
- Use subset of **LAION-400M** (for advanced users): [https://laion.ai/blog/laion-400-open-dataset/](https://laion.ai/blog/laion-400-open-dataset/)

## 📄 Requirements
Example `requirements.txt`:
```
torch
transformers
faiss-cpu
numpy
pandas
streamlit
Pillow
tqdm
```

## 🐳 Docker Support
```dockerfile
# Dockerfile
FROM python:3.10-slim
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
CMD ["streamlit", "run", "app/streamlit_app.py"]
```

## 📘 License
MIT License

## 👨‍💻 Author
[Your Name](https://github.com/yourusername)

## 📎 Acknowledgements
- OpenAI’s [CLIP paper](https://arxiv.org/abs/2103.00020)
- Facebook AI’s [FAISS](https://github.com/facebookresearch/faiss)
- MS-COCO dataset authors
