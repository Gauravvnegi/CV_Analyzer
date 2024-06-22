Features

1. Resume Parsing
   The Resume Analyzer parses resumes in various formats, including PDF, DOCX, and plain text. It extracts textual content, preserving the original formatting for easy readability.

2. Information Extraction
   Key information such as name, contact details, education, work experience, skills, and certifications is automatically extracted from the resume.

3. Keyword Matching
   The tool identifies relevant keywords or phrases specified by the user to highlight essential qualifications or skills required for a job position.

4. Sentiment Analysis
   The tool can perform sentiment analysis on the resume content, providing insights into the candidate's attitude and tone.

5. Skill Matching
   By comparing the extracted skills from the resume with a predefined list of required skills, the tool helps determine the candidate's suitability for a specific role.

6. Customizable Scoring
   Users can define scoring criteria based on the importance of various resume sections (e.g., education, experience) to calculate an overall score for each resume.

7. Summary Generation
   The tool generates a concise summary of the resume, highlighting the most relevant information and providing an overall assessment.Features
8. Resume Parsing
   The Resume Analyzer parses resumes in various formats, including PDF, DOCX, and plain text. It extracts textual content, preserving the original formatting for easy readability.

9. Information Extraction
   Key information such as name, contact details, education, work experience, skills, and certifications is automatically extracted from the resume.

10. Keyword Matching
    The tool identifies relevant keywords or phrases specified by the user to highlight essential qualifications or skills required for a job position.

11. Sentiment Analysis
    The tool can perform sentiment analysis on the resume content, providing insights into the candidate's attitude and tone.

12. Skill Matching
    By comparing the extracted skills from the resume with a predefined list of required skills, the tool helps determine the candidate's suitability for a specific role.

13. Customizable Scoring
    Users can define scoring criteria based on the importance of various resume sections (e.g., education, experience) to calculate an overall score for each resume.

14. Summary Generation
    The tool generates a concise summary of the resume, highlighting the most relevant information and providing an overall assessment.

The specific machine learning model used in this code is the "paraphrase-MiniLM-L6-v2" model from SentenceTransformer. It's a pre-trained transformer-based model designed for encoding sentences into dense vector representations. The SentenceTransformer library, in general, uses various transformer architectures for training its models, and the details of the underlying transformer architecture are encapsulated within the pre-trained models provided by the library.

/////
Libraries and Dependencies:

The project utilizes several Python libraries, including Streamlit, NLTK, Spacy, PyMySQL, PIL (Pillow), and others.
It downloads NLTK stopwords and loads the English language model for spaCy.
Resume Parsing:

The pyresparser library is used for parsing resume data from PDF files.
The pdf_reader function extracts text content from PDF files using PDFMiner.
Courses and Certificates Recommendations:

The application recommends courses and certificates based on the skills identified in the user's resume.
Courses are categorized into Data Science, Web Development, Android Development, iOS Development, and UI-UX Development.
Recommendations are generated using sentence embeddings and cosine similarity.
Database Integration:

The project uses a MySQL database to store user data, including details like name, email, resume score, timestamp, etc.
There's a function (insert_data) for inserting user data into the database.
User Interface (UI):

Streamlit is used for building the web-based user interface.
Users can upload their resumes (in PDF format) and get recommendations for skills, courses, and certificates.
The UI includes sliders, tags for skills, and displays recommendations.
Admin Panel:

There is an admin section with login functionality.
Once logged in, the admin can view user data, including details like resume scores, predicted fields, and recommended skills/courses.
Admins can also download a CSV report of user data.
Data Visualization:

The project includes data visualization using Plotly Express for generating pie charts.
Pie charts represent the distribution of predicted fields and user experience levels based on the stored user data.
YouTube Video Integration:

YouTube videos related to resume writing tips and interview preparation are embedded in the UI.
Videos are randomly selected from predefined lists (resume_videos and interview_videos).
Security Considerations:

There's a basic admin authentication mechanism with a hardcoded username and password.
Project Structure:

The project seems to be organized into functions, making it modular and easier to understand.
Deployment:

The Streamlit app is deployed locally, allowing users to access it through a web browser.

///

The choice of using Streamlit over HTML, CSS, JavaScript, or other tools depends on the project requirements, ease of development, and the intended audience. Here are some reasons why Streamlit might be a suitable choice for this project:

Simplicity and Rapid Development:

Streamlit is designed for simplicity and rapid prototyping. It allows developers to create interactive web applications with minimal effort and code.
The project code appears concise, making it easy to understand and maintain.
Python-Based:

Streamlit is a Python library, which can be advantageous if the development team is more comfortable with Python.
It eliminates the need for additional languages like HTML, CSS, or JavaScript, which might be required in traditional web development.
Data Science Integration:

Streamlit is popular among data scientists and analysts for creating interactive data visualizations and dashboards.
In this project, where data analysis and visualization are key components, Streamlit provides a seamless integration with data science workflows.
Built-In Widgets:

Streamlit provides built-in widgets like sliders, file uploaders, tags, etc., making it easy to create interactive elements without extensive HTML or JavaScript knowledge.
Embedding Python Code:

Streamlit allows developers to embed Python code directly within the application, enabling dynamic content generation and interaction.
Deployment Convenience:

Streamlit apps can be easily deployed using Streamlit sharing or other hosting platforms, requiring minimal configuration compared to setting up a traditional web server for HTML, CSS, and JavaScript.
Focus on Data Applications:

Streamlit is specifically designed for creating data-centric applications and dashboards. It provides features tailored to data analysis and visualization tasks.
Community and Documentation:

Streamlit has an active community and comprehensive documentation, making it easier for developers to find support and resources.

In the modified code, the SentenceTransformer is used to encode the resume skills and predefined keywords into dense vectors (embeddings). These embeddings capture the semantic meaning of the skills and keywords in a continuous vector space. The cosine similarity between these embeddings is then calculated to measure the similarity between the resume skills and predefined keywords for different fields (Data Science, Web Development, Android Development, IOS Development, UI-UX Development).

Here's a breakdown of the use:

Embedding Skills and Keywords:

The SentenceTransformer model is initialized with the specified architecture ('paraphrase-MiniLM-L6-v2').
The resume skills and predefined keywords for each field are encoded into dense vectors using the encode method of the SentenceTransformer model.
Calculating Cosine Similarity:

The cosine similarity is calculated between the resume skills and the predefined keyword embeddings for each field.
This similarity measure indicates how close or similar the resume skills are to the skills associated with each field.
Field Recommendation:

The field with the highest average cosine similarity is selected as the recommended field for the candidate.
This recommendation is based on the assumption that the candidate's skills are more similar to the skills of a particular field.
Displaying Recommended Courses:

Finally, the code displays a specified number of recommended courses for the chosen field.
In summary, by using Sentence Transformer, you leverage pre-trained models that understand the semantic meaning of words and phrases, allowing for a more sophisticated comparison of skills and better field recommendations based on the semantic similarity between the candidate's skills and predefined keyword sets.
