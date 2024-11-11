# Patent Autofill Engine
### Demo Video
https://app.filmora.io/#/object/csp1lcb5jr1u7ttpnq9g

# User Flow
1. Upload a document contains content about patent application
2. Gemini-Pro automatically extract the data which are required to fill out US-patent application

# Technical Considerations
### Streamlit and VertexAI Integration
- Handling the integration between the Streamlit file uploader widget and the VertexAI API posed a challenge, as detailed below:
  - The Streamlit file uploader stores the uploaded file as a 'file-like' object.
  - To interact with the VertexAI API, this object must be converted into a data stream using `uploaded_file.getbuffer()` method.
  - Then the byte file should be saved as a temporary file using `tempfile` library.
  - The byte stream is then passed to the VertexAI API, where it is converted into an image format compatible with VertexAI using the `genai.upload_file(f.name, mime_type="application/pdf")` method.

### Convert VertexAI output into JSON object
- JSON form is efficient to handle the data, but the type of the llm output is str, so it is required to be converted into JSON file. 
- configure llm output type: `model = genai.GenerativeModel("gemini-1.5-pro-latest", generation_config={"response_mime_type": "application/json"})`
- convert the output into json: `json.loads(response.text)`

### Populate html file dynamically with data
- Use library: `from jinja2 import Template`
- Save the data in dictionary form, then render the data into html: `output = template.render(data)`
- Fetch the data in html file  

### Gemini Flash vs. Pro:
- After comparing the Gemini Flash and Pro versions in terms of performance and cost, we chose to proceed with the Pro version due to its optimized balance of both.

# License
- Source code is proprietary and cannot be shared, as it is a resource of Jigo Incorporation.

# Tech Stacks
- Streamlit
- Python
- VertexAI APIs
- GCP SDK
