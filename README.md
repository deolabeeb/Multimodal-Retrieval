# 🧠 Multimodal Retrieval with CLIP & FAISS

A Python project that enables **text-to-image** and **image-to-text** retrieval using **OpenAI's CLIP** model and **FAISS** for efficient similarity search.

---

## 🚀 Features

- 🔍 Retrieve images using text queries (e.g., “a cat on a sofa”)
- 🔁 Retrieve captions using image uploads
- ⚡ Fast vector similarity search via Facebook’s FAISS
- 🌐 Streamlit UI for quick testing

---

## 🧰 Tech Stack

- [OpenAI CLIP](https://huggingface.co/openai/clip-vit-base-patch32) via Hugging Face
- [FAISS](https://github.com/facebookresearch/faiss)
- [Streamlit](https://streamlit.io/) or [FastAPI](https://fastapi.tiangolo.com/)
- Python libraries: `torch`, `transformers`, `PIL`, `faiss-cpu`, `numpy`, `streamlit`

---

## 📦 Dataset

We're using a small subset of **MS-COCO** (Common Objects in Context) dataset:

- **Images + Captions:** [MS-COCO 2017](https://cocodataset.org/#download)  
- For demo: Download **2017 Val Images [5K]** and **captions_val2017.json**

Download instructions:

```bash
wget http://images.cocodataset.org/zips/val2017.zip
wget http://images.cocodataset.org/annotations/annotations_trainval2017.zip
