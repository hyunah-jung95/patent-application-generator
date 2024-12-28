# Patent Application Generator
This application streamlines the process for _U.S. patent lawyers_ by automatically generating patent application forms (IDS).<br>
Users can interactively review and edit the forms through an intuitive HTML interface,<br> 
significantly enhancing their efficiency and accuracy.

[👉 Go to Live APP](https://patent-application-generator-787703115620.us-west1.run.app)

# User Flow
<img width="600" alt="image" src="https://github.com/user-attachments/assets/f37a216c-4ffa-428e-8601-51196f1c2968" />
<img width="600" alt="image" src="https://github.com/user-attachments/assets/47e53105-312a-4e00-a686-5f71dfee75bb" />


1.  Upload documents related to the patent (e.g., foreign forms, descriptions).
2.	Extract and analyze data to match U.S. patent application requirements.
3.	Automatically populate an editable HTML form with the refined data.
4.	Users review, edit, and finalize the form interactively.
5.	Save or print the completed form for submission.


# Key Features
- **Specialized**: Tailored for U.S. patent lawyers to address specific workflow challenges.
- **High Accuracy**: Delivers 99% accuracy, validated by partner patent lawyers.
- **Multilingual Support**: Processes documents in multiple languages (e.g., English, Chinese, Korean).
- **Scalable**: Handles multiple document uploads and diverse PDF formats (image/text).

# My Contributions 
- _Designed_ the architecture, collaborating with a PM and patent lawyer to align with client business requirements.
- _Developed_ backend logic using Python and created a user-friendly frontend UI with Streamlit.
- _Deployed_ the app using CI/CD pipelines on GCP, ensuring reliability and scalability.

# Technical Highlights
1. Streamlit and VertexAI Integration: Managed file uploads as streams and converted data for compatibility with VertexAI.
2. JSON Conversion: Configured LLM output to JSON for structured handling of generated data.
3.	Dynamic HTML Rendering: Used Jinja2 templates to populate and dynamically render data in the HTML form.

# License
- Associated with Jigo.ai, which holds the app’s license.

# Tech Stacks
- Programming: Python, Streamlit
- Gloud Platform: GCP
