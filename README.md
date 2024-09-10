# Patent Autofill Engine
https://github.com/user-attachments/assets/6dc60f04-d31e-491e-9260-42eb4ac56fde

# User Flow
1. Upload a document contains content about patent application
2. Gemini-Pro automatically extract the data which are required to fill out US-patent application

# Technical Considerations
## Streamlit and VertexAI Integration
- Handling the integration between the Streamlit file uploader widget and the VertexAI API posed a challenge, as detailed below:
  - The Streamlit file uploader stores the uploaded file as a 'file-like' object.
  - To interact with the VertexAI API, this object must be converted into a data stream using `uploaded_file.getbuffer()` method.
  - Then the byte file should be saved as a temporary file using `tempfile` library.
  - The byte stream is then passed to the VertexAI API, where it is converted into an image format compatible with VertexAI using the `genai.upload_file(f.name, mime_type="application/pdf")` method.
 
## Gemini Flash vs. Pro:
- After comparing the Gemini Flash and Pro versions in terms of performance and cost, we chose to proceed with the Pro version due to its optimized balance of both.

# License
- Source code is proprietary and cannot be shared, as it is a resource of Jigo Incorporation.

# Tech Stacks
- Streamlit
- Python
- VertexAI APIs
- GCP SDK
