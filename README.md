# ask-your-data
A simple, flexible Retrieval-Augmented Generation (RAG) app that lets you ask questions about your own files or any webpage using powerful Large Language Models (LLMs) via LangChain and Gemini.  
Supports `.txt`, `.pdf`, and webpage sources with automatic chunking, embedding, and concise answer generation.

## How to Use

### 1. Install Requirements

Open a terminal and run:
```
pip install langchain langchain-community langchain-google-genai faiss-cpu pypdf
```

### 2. Prepare Your Data

- You can use either a `.txt` or `.pdf` file, or a webpage as your data source.
- For files, place your `.txt` or `.pdf` file inside the `data/` directory (e.g., `data/myfile.txt` or `data/myfile.pdf`).
- For webpages, simply have the URL ready.

### 3. Set Your Gemini API Key as an Environment Variable

You must set your Gemini API key before running the notebook so the app can access Gemini services.

**On Windows (Command Prompt):**
1. Open Command Prompt.
2. Run:
   ```
   set GOOGLE_API_KEY=YOUR_GEMINI_API_KEY
   ```
3. Start VS Code or Jupyter from the same Command Prompt window:
   ```
   code
   ```
   or
   ```
   jupyter notebook
   ```

**On macOS/Linux (bash):**
1. Open Terminal.
2. Run:
   ```
   export GOOGLE_API_KEY=YOUR_GEMINI_API_KEY
   ```
3. Start VS Code or Jupyter from the same terminal window:
   ```
   code
   ```
   or
   ```
   jupyter notebook
   ```

**Alternative (Quick Test Only):**
You can also set the API key at the top of your notebook (not recommended for sharing):
```python
import os
os.environ["GOOGLE_API_KEY"] = "YOUR_GEMINI_API_KEY"
```

**Warning:**  
Never hardcode your actual API key directly in the notebook or source code if you plan to share or publish your code. Hardcoding credentials can expose your key to unauthorized users and may result in security risks or unexpected charges. Always use environment variables or secure secret management for sensitive information.

> **Note:** The API key must be set in the same environment/session where you launch Jupyter or VS Code, or your notebook will not be able to access it.

### 4. Run the Notebook

- Open `QnA.ipynb` in Jupyter or VS Code.
- Run all cells in order.
- When prompted:
  - Enter `file` to use a local file, or `webpage` to use a webpage as your data source.
  - If you chose `file`, enter the file path (e.g., `data/myfile.txt` or `data/myfile.pdf`).
  - If you chose `webpage`, enter the full URL of the webpage.
  - Enter your question when prompted.

### Notes

- The code automatically detects if your file is a `.txt` or `.pdf` and loads it accordingly, or loads content from a webpage.
- Make sure your file is not empty and is placed in the correct directory if using a file.
- The output will be a concise answer generated from your document or webpage, using Gemini.

---

### Disclaimer

- Webpage loading relies on extracting visible text from the HTML. Some complex or JavaScript-heavy pages may not be processed correctly, and only static text content will be available for question answering.
- Always ensure you have permission to access and process the content of any webpage you use.
- The quality and completeness of answers depend on the quality and structure of the source content.
