# AIBuddy - AI Chatbot API

## Overview

AIBuddy is an AI Chatbot API that allows you to integrate advanced AI capabilities into your applications. This API is built using Python and the Flask framework, leveraging various external services for enhanced functionality.

## Features

1. **Chatbot Functionality:** AIBuddy uses the Bard API for chatbot capabilities, providing natural language processing and conversation management.

2. **Image Recognition Endpoint:** A dedicated endpoint is provided for image recognition using the Imagga API. This enables your application to analyze and understand the content of images.

3. **Generate Image:** A separate endpoint utilizes the stability.ai API to generate images, adding a creative aspect to your application.

4. **Q&A Using Google PALM:** AIBuddy integrates Google PALM for question and answer capabilities, enhancing its ability to provide valuable information.

5. **URL Summary:** AIBuddy extracts summaries from URLs, allowing users to quickly understand the content of web pages.

6. **OCR (Optical Character Recognition):** The API supports extracting text from images using the api.ocr.space service, enabling your application to process text present in images.

7. **File Summary Generation:** The Bard API is employed to generate summaries for files, providing concise information about the content.

## Dependencies

- **Python:** AIBuddy is built using Python, ensuring ease of integration and compatibility.

- **Flask:** The Flask framework is utilized for creating the web API, offering a lightweight and flexible solution for web development.

- **Bard API:** Integrated for chatbot functionality and file summary generation.

- **Imagga API:** Used for image recognition capabilities.

- **stability.ai API:** Employed for generating images.

- **Google PALM:** Integrated for advanced question and answer capabilities.

- **api.ocr.space:** Utilized for OCR (Optical Character Recognition) to extract text from images.

## Configuration

To use AIBuddy, you need to set up your environment variables. Create an `.env` file in the root directory with the following content:

```env
BARD_API_KEY="Your_Bard_API_Key"
OCR_KEY="Your_OCR_API_Key"
CLOUDINARY_CLOUD_NAME="Your_Cloudinary_Cloud_Name"
CLOUDNARY_API_KEY="Your_Cloudinary_API_Key"
CLOUDINARY_SECRET="Your_Cloudinary_Secret"
STABILITY_AUTH="Your_Stability_Authentication_Key"
imagga_api_key="Your_Imagga_API_Key"
imagga_api_secret="Your_Imagga_API_Secret"
BARD_TOKEN="Your_Bard_Token"
```

Replace the placeholder values with your actual API keys and tokens.

## Usage

1. Install the required dependencies:

   ```bash
   pip install -r req.txt
   ```

2. Run the Flask application:

   ```bash
   python app.py
   ```

3. Access the API at `http://localhost:5000`.

## Example Requests

### Chatbot:
```bash
curl -X POST -H "Content-Type: application/json" -d '{"message": "Hello, AIBuddy!"}' http://localhost:5000/chat
```

### Image Recognition:
```bash
curl -X POST -H "Content-Type: multipart/form-data" -F "image=@path/to/image.jpg" http://localhost:5000/imagerecognition
```

### Generate Image:
```bash
curl -X -H "Content-Type: application/json" -d '{"prompt": "prompt to generate image!"}' POST http://localhost:5000/generateimage
```

### Q&A using Google PALM:
```bash
curl -X POST -H "Content-Type: application/json" -d '{"question": "What is the capital of France?"}' http://localhost:5000/qna
```

### URL Summary:
```bash
curl -X POST -H "Content-Type: application/json" -d '{"url": "https://example.com"}' http://localhost:5000/url
```

### OCR (Text in Image):
```bash
curl -X POST -H "Content-Type: multipart/form-data" -F "image=@path/to/image_with_text.png" http://localhost:5000/ocr
```

### File Summary Generation:
```bash
curl -X POST -H "Content-Type: multipart/form-data" -F "file=@path/to/document.docx" http://localhost:5000/upload
```

Feel free to customize the API calls based on your application's needs.
