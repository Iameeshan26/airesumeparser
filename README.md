# AI Resume Parser

An intelligent resume parsing application powered by AI that automatically extracts and analyzes key information from resume files. This tool uses Google's Gemini 2.5 Flash model to intelligently parse resumes and provide structured data along with a resume score and suggested job roles.

## Features

- **Multi-Format Support**: Parse resumes in PDF, DOCX, and TXT formats
- **AI-Powered Extraction**: Uses Google's Gemini 2.5 Flash API for intelligent resume parsing
- **Structured Output**: Extracts information including:
  - Personal Details (Name, Email, Phone)
  - Work Experience (Job titles, Companies, Dates, Descriptions)
  - Education (Degrees, Institutions, Graduation Dates)
  - Skills (Technical Skills, Soft Skills, Certifications)
  - Professional Summary
- **Resume Scoring**: Intelligent scoring system (0-10) based on:
  - Number and variety of technical skills
  - Work experience depth and quality
  - Use of action verbs and achievement-oriented language
- **Job Role Suggestions**: Automatically suggests suitable job roles based on detected skills
- **JSON Export**: Download parsed resume data as JSON for further processing
- **Responsive Design**: Clean, modern UI built with Tailwind CSS

## How It Works

1. **File Upload**: Select a resume file (PDF, DOCX, or TXT)
2. **Text Extraction**: The application extracts text from the uploaded file:
   - PDF files are processed using PDF.js library
   - DOCX files are processed using Mammoth.js library
   - TXT files are read directly
3. **AI Parsing**: The extracted text is sent to Google's Gemini API with a detailed schema for structured extraction
4. **Analysis & Scoring**: The parsed data is analyzed to generate:
   - Resume quality score
   - Suggested job roles based on skills detected
5. **Display & Download**: Results are displayed in a formatted view with an option to download the raw JSON data

## Scoring System

The resume score (0-10) is calculated based on:

- **Skills Score** (0-4 points): 1 point for every 4 technical skills
- **Experience Score** (0-6 points):
  - Up to 3 points from number of work experience entries
  - Up to 3 points from description quality (length and action verbs)
  - Bonus points awarded for use of achievement-oriented action verbs (achieved, managed, led, developed, implemented, etc.)

## Technology Stack

- **Frontend**: HTML5, Tailwind CSS
- **PDF Processing**: PDF.js (v2.11.338)
- **DOCX Processing**: Mammoth.js (v1.4.18)
- **AI Model**: Google Gemini 2.5 Flash API
- **Structured Output**: JSON Schema validation

## Getting Started

1. Clone or download this repository
2. Open `index.html` in a modern web browser
3. Click "Upload Resume File" and select your resume
4. Click "Parse Resume" to extract information
5. View the results and optionally download as JSON

## File Structure

```
├── index.html          # Main application with embedded JavaScript
├── parserstyles.css    # Custom CSS styles
└── README.md          # This file
```

## Demo Screenshots

Below are screenshots showing the AI Resume Parser in action:

### Screenshot 1 - Upload Interface

![AI Resume Parser Upload Interface](./demo-screenshot-1.png)

## Requirements

- Modern web browser with JavaScript enabled
- Internet connection (for Gemini API calls and CDN resources)
- Valid resume file (PDF, DOCX, or TXT format)
- Google API Key (required for Gemini API access)

## API Configuration

The application uses Google's Gemini 2.5 Flash API. The API key is currently embedded in the code. For production use, consider:

- Using environment variables or backend proxies
- Implementing proper authentication
- Rate limiting and error handling

## Browser Compatibility

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Any modern browser with ES6 JavaScript support

## Error Handling

The application includes robust error handling for:

- Invalid or corrupted files
- API failures with automatic retry (up to 3 attempts with exponential backoff)
- Empty files or image-based resumes
- Network errors

## Future Enhancements

- Support for additional resume formats
- Resume comparison and benchmarking
- ATS keyword optimization suggestions
- Resume quality improvement recommendations
- Database storage for parsed resumes

## License

This project is provided as-is for educational and professional use.

## Support

For issues or questions, please check the browser console for detailed error messages and ensure all required libraries are loading correctly.
