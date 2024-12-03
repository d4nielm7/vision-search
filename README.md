# Vision Search: Image Recognition with Deep Learning

This folder contains an implementation of an **Image Recognition Similarity System** using **Deep Learning**. The system is designed to find similar images in a dataset based on embeddings and cosine similarity. It leverages **OpenCLIP embeddings** and **ChromaDB** for indexing and searching.

---

## **Contents**
### Files
- **`vision_search.ipynb`**: Jupyter Notebook containing the full implementation for:
  - Loading and processing image datasets.
  - Creating and saving image embeddings.
  - Searching for visually similar images.
- **`fashion.csv`**: Sample dataset containing image paths and metadata for testing the system.
- **`image_simi_db`**: Folder for storing ChromaDB persistent data.

---

## **Setup and Installation**

### **Prerequisites**
- Python 3.8+ installed on your system.
- Required libraries:
 ```bash
pip install numpy pandas torch langchain-chroma>=0.1.2 chromadb matplotlib tqdm base64
```
---

## **Steps to Run**

### **Step 1: Open the Jupyter Notebook**
- Open the `vision_search.ipynb` file in your preferred Jupyter Notebook environment.

### **Step 2: Run the Notebook**
- Follow the cells in the notebook to:
  1. **Load the Dataset**: Import the sample image paths and metadata.
  2. **Process Images**:
     - If a saved checkpoint (`final_data.pkl`) exists:
       - The embeddings and metadata will be loaded automatically, skipping training.
     - If no checkpoint exists:
       - Generate embeddings for all images using the **OpenCLIP** model.
       - Save the embeddings and metadata for future use.
  3. **Perform Similarity Search**:
     - Use the trained embeddings to find similar images.
     - Visualize the query image and the top-K similar results.

---

## **Key Features**

### **1. Image Embedding Creation**
- Embeddings are generated for each image using **OpenCLIP** (ViT-L-14 architecture).
- These embeddings represent the semantic content of the images in a high-dimensional space.

### **2. ChromaDB Integration**
- Embeddings are indexed and stored in **ChromaDB** for efficient search.
- Persistent storage ensures embeddings don’t need to be regenerated for future queries.

### **3. Visual Similarity Search**
- The system finds the top-K similar images to a query image using **cosine similarity**.
- Results include the query image, metadata, and visualized similar images.

---

## **Outputs**
- **Query Image**: Displays the input image for the similarity search.
- **Top-K Results**:
  - Visually similar images based on embeddings.
  - Associated metadata (e.g., description, tags, specifications).

---

## **Insights**
- **Saved Checkpoints**: If embeddings are already saved (`final_data.pkl`), the training step can be skipped to save time.
- **Efficient Retrieval**: By using embeddings and ChromaDB, the system provides fast and accurate image retrieval.
- **Scalability**: The approach can handle large datasets by efficiently storing and querying embeddings.

---

## **Use Cases**
- Visual search systems for e-commerce platforms (e.g., find products similar to an uploaded image).
- Organizing and finding duplicates in large image datasets.
- Content-based filtering for images in recommendation systems.

