# AI Feedback Assistant

A Python script that leverages the Google Gemini API to automate the generation of first-draft feedback for student writing assignments, helping educators save time and focus on providing higher-level, personalized comments.

## Motivation
Providing timely and detailed feedback is crucial for student learning but can be a time-consuming process for instructors, especially in large classes. This tool was created to streamline that workflow by handling the initial pass of feedback generation based on a specific rubric and assignment context.

## Features
- Automates feedback generation for a batch of student papers.
- Reads both `.docx` and `.pdf` file formats.
- Interacts with the Google Gemini API for powerful text analysis and generation.
- Utilizes a highly customizable prompt structure, including:
    - The full assignment description for context.
    - An example of high-quality feedback to guide the AI's tone and style.
    - A structured template for the final output.
- Handles common Canvas filename conventions (`username_id_...`).
- Securely manages API keys using environment variables.

## Tech Stack
- **Language:** Python 3
- **AI/NLP:** Google Gemini API (`google-generativeai`)
- **File Handling:** `python-docx`, `PyPDF2`

## Setup & Installation
1.  **Clone the repository:**
    ```bash
    git clone https://github.com/YourUsername/AI-Feedback-Assistant.git
    cd AI-Feedback-Assistant
    ```
2.  **Create and activate a Python virtual environment:**
    ```bash
    python -m venv venv
    # On Windows
    venv\Scripts\activate
    # On MacOS/Linux
    source venv/bin/activate
    ```
3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Set up your API Key:** This script requires a Google Gemini API key. You must set it as an environment variable named `GOOGLE_API_KEY`.
    ```bash
    # On MacOS/Linux (for the current session)
    export GOOGLE_API_KEY="YOUR_API_KEY_HERE"

    # On Windows (Command Prompt, for the current session)
    set GOOGLE_API_KEY=YOUR_API_KEY_HERE
    ```
    *For permanent setup, search for instructions on setting environment variables for your specific OS.*

## Usage
1.  Place all student papers (as `.docx` or `.pdf` files) into a folder named `papers` in the root of the project directory.
2.  Run the script from the terminal:
    ```bash
    python generate_feedback.py
    ```
3.  The script will process each file and save the generated feedback as a `.txt` file in the `feedback` folder.
4.  **MANDATORY: Review and edit every generated file.** The output is an AI-generated draft. It must be reviewed for accuracy, tone, and personalization by the instructor before being shared with students.

## Ethical Considerations
This tool is designed as an *instructor's assistant*, not a replacement for human judgment.
- **Student Privacy:** Users should be mindful of their institution's policies (e.g., FERPA in the US) regarding the use of third-party services with student data. This script uses the Google Gemini API, whose standard policy is not to use API data for training their models.
- **Instructor Oversight:** The quality and appropriateness of all final feedback remain the full responsibility of the instructor.

## Future Improvements
- [ ] Integrate the Google Docs API to handle GDoc links directly.
- [ ] Add support for a class roster CSV to automatically map usernames to full names.
- [ ] Create a simple GUI (e.g., with Tkinter or PyQt) for easier use.
