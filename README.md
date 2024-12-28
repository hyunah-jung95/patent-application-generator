# Patent Application Generator
This application is developed for patent lawyers who have to fill out US patent application forms(IDS).
The app automatically generates application forms by extracting data from large amout of related documents.

After the app complete the form, users can edit it interactively simply by clicking buttons of the HTML form.
This app innovately enhances the effectiveness of patent lawyers by automation and validation of form. 

[👉 Go to Live APP](https://patent-application-generator-787703115620.us-west1.run.app)

# User Flow
1. User uploads documents related to the patent application contents(e.g. foreign application forms, patent descriptions)
2. The app analyzes the uploaded documents and extracts data matched with US-patent application requirements.
3. Parse and refine extracted data and fill out HTML form. 
4. Users review the form and add, delete and edit each line of the filled data.
5. User can save or print the application form to be ready to submit to the patent department.

# Key Features
- **Speciality**: The app is focused on the handful problem with patent lawyers in US.
- **Accuracy**: The accuracy of the completed form is 99%, which is validated by the patent lawyer in partnership.
- **Compatibility**: The app can be applied to multiple languages(e.g. English, Chinese, Korean, etc.), and variety of types of pdf can be readable(image, text, etc.)
- **Scalability**: Multiple documents can be uploaded and can be handled.

# My Contributions 
- _Designed_ the architecture, collaborating with the PM and patent lawyer to align with client business requirements.
- _Developed_ backend logic using Python and created a user-friendly frontend UI with Streamlit.
- _Deployed_ the app using CI/CD pipelines on GCP, ensuring reliability and scalability.

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

# License
- This app is associated with jigo.ai
- The license is owned by jigo.ai

# Tech Stacks
- Programming: Python, Streamlit
- Gloud Platform: GCP
