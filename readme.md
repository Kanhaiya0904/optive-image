👤 Author
Kanhaiya Kumar
GitHub: @Kanhaiya0904

# IMAGE-ANONYMIZER

An intelligent image anonymization tool that automatically detects and blurs sensitive information in images using AI-powered OCR, NER (Named Entity Recognition), and pattern matching.

## 🌟 Features

- **Multi-Layer Detection**: Combines OCR, NER, and regex patterns for comprehensive sensitive data detection
- **AI-Powered Selection**: Uses Google Gemini AI to intelligently identify sensitive content
- **Smart Blurring**: Applies Gaussian blur to detected sensitive regions while preserving image layout
- **REST API**: FastAPI-based web service for easy integration
- **Batch Processing**: Process multiple images efficiently
- **Customizable Rules**: Configure detection patterns via [instructions.txt](cci:7://file:///c:/Users/kanahaiya%20kumar/Desktop/optive-image-purge-master/optive-image-purge-master/instructions.txt:0:0-0:0)

## 🔍 What Gets Detected & Anonymized

- **Personal Information**: Names, addresses, phone numbers, email addresses
- **Financial Data**: Bank account numbers, IBAN, IFSC, SWIFT codes, credit card numbers
- **Identification**: Employee IDs, SSN, passport numbers, license numbers
- **Dates & Times**: Issue dates, expiry dates, birth dates
- **Custom Patterns**: Configurable via regex and AI instructions

## 🏗️ Architecture

The anonymization pipeline consists of:

1. **OCR Extraction** (EasyOCR) - Extracts text with bounding boxes
2. **Token Grouping** - Clusters text into logical lines
3. **Gemini AI Analysis** - AI-assisted sensitive content identification
4. **Rule-Based Detection** - Regex patterns for emails, phones, IDs, etc.
5. **NER Detection** - Presidio + spaCy for entity recognition
6. **Smart Blurring** - OpenCV Gaussian blur on detected regions

## 📋 Prerequisites

- Python 3.8+
- Google Gemini API Key (get one from [Google AI Studio](https://makersuite.google.com/app/apikey))


IMAGE-ANONYMIZER/
├── input_images/          # Place images to anonymize here
├── output_images/         # Anonymized images output
├── utils/
│   └── image_utils.py    # Core anonymization logic
├── main.py               # CLI entry point
├── api.py                # FastAPI REST service
├── instructions.txt      # AI detection instructions
├── requirements.txt      # Python dependencies
├── .env.example          # Environment variables template
└── README.md

##Identify and mark tokens containing:
- Personal names
- Email addresses
- Phone numbers
- Addresses
- Financial information
- ID numbers

kernel_size = max(5, min(w, h) // 10)  # Adjust divisor for more/less blur


##🛠️ Technologies Used
OCR: EasyOCR
AI: Google Gemini 1.5 Flash
NER: Presidio Analyzer + spaCy
Image Processing: OpenCV, Pillow
API: FastAPI, Uvicorn
Environment: python-dotenv


##📊 Performance Notes
OCR accuracy depends on image quality
Processing time scales with image size and text density
Gemini API calls may add latency (typically 1-3 seconds per image)
spaCy's small model prioritizes speed; upgrade to en_core_web_lg for better accuracy

##🔒 Security & Privacy
API keys are protected via 
.gitignore
Output directories are excluded from version control
All processing happens locally (except Gemini API calls)
No data is stored or logged permanently

##🚧 Future Improvements
 Add page/region-level de-duplication
 Persist debug overlays for QA
 CLI switches for toggling features
 Support for multiple languages
 Batch API endpoint
 Docker containerization
 GPU acceleration for OCR

