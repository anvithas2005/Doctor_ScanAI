# Doctor_ScanAI

MediScanAI is an AI-powered medical report analysis tool. It uses specialist agents (Cardiologist, Psychologist, Pulmonologist) and a multidisciplinary team to analyze patient reports and provide possible diagnoses and recommendations.

## Features

- Upload a `.txt` medical report via a web interface.
- Each specialist agent analyzes the report and provides their assessment.
- A multidisciplinary team agent reviews all specialist outputs and generates a final diagnosis.
- Results are saved to `results/final_diagnosis.txt` and displayed on the web interface.

## Setup

1. **Clone the repository** and navigate to the project directory.

2. **Create a virtual environment** (if not already created):

   ```powershell
   python -m venv .venv
   ```

3. **Activate the virtual environment**:

   ```powershell
   .venv\Scripts\activate
   ```

4. **Install dependencies**:

   ```powershell
   pip install -r requirements.txt
   ```

   If `requirements.txt` is missing, install manually:
   ```powershell
   pip install flask langchain langchain-core langchain-community langchain-openai langchain-groq openai tiktoken pydantic aiohttp tenacity
   ```

5. **Set up your API keys**  
   Copy `.env.example` to `.env` and add your Groq API key:

   ```powershell
   copy .env.example .env
   # Then edit .env and set GROQ_API_KEY=your_actual_key
   ```

   Or set the environment variable manually:
   ```powershell
   $env:GROQ_API_KEY="your_actual_key"
   ```

## Usage

### Command Line

To analyze a sample report and save the diagnosis:

```powershell
python main.py
```

### Web Application

To start the Flask web server:

```powershell
python app.py
```

Then open your browser and go to [http://127.0.0.1:5000](http://127.0.0.1:5000) to upload a medical report and view the diagnosis.

## Project Structure

```
main.py
app.py
Utils/
    Agent.py
uploads/
results/
```

- `main.py`: Command-line interface for running the analysis.
- `app.py`: Flask web application.
- `Utils/Agent.py`: Agent classes for medical analysis.
- `uploads/`: Uploaded reports.
- `results/`: Final diagnosis output.

## License

This project is for educational and research purposes only.
