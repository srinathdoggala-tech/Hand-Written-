## 📑 Table of Contents

- [AssignMe - Complete Your Assignments with Custom Handwriting](#assignme---complete-your-assignments-with-custom-handwriting)
- [🛡️ Open Source](#️-open-source)
- [🌟 Features](#-features)
  - [1. Assignment Text to Handwriting Converter](#1-assignment-text-to-handwriting-converter)
  - [2. Custom Handwriting Font Generator](#2-custom-handwriting-font-generator)
  - [3. AI-Powered Q&A System](#3-ai-powered-qa-system)
  - [4. Advanced Font Processing Backend](#4-advanced-font-processing-backend)
- [🖼️ System Architecture](#️-system-architecture)
- [🚀 Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Backend Services Setup (Optional)](#backend-services-setup-optional)
- [📚 Usage](#-usage)
  - [Converting Text to Handwriting](#converting-text-to-handwriting)
  - [Creating Your Own Handwriting Font](#creating-your-own-handwriting-font)
- [🔧 Customization Options](#-customization-options)
  - [Handwriting Options](#handwriting-options)
- [📂 Project Structure](#-project-structure)
- [🏗️ Architecture Overview](#️-architecture-overview)
  - [Frontend Components](#frontend-components)
  - [Backend Services](#backend-services)
  - [Key Features](#key-features)
- [🔄 API Integration](#-api-integration)
  - [Main File Processing API](#main-file-processing-api)
  - [FontForge Backend API](#fontforge-backend-api)
  - [Gemini Q&A API](#gemini-qa-api)
- [🐳 Docker Deployment](#-docker-deployment)
  - [FontForge Backend](#fontforge-backend)
- [🤖 AI Features](#-ai-features)
  - [Gemini Integration](#gemini-integration)
  - [Setup Requirements](#setup-requirements)
- [🤝 Contributing](#-contributing)
  - [Development Areas](#development-areas)
- [📝 License](#-license)
- [👥 Acknowledgments](#-acknowledgments)

# AssignMe - Complete Your Assignments with Custom Handwriting

[![GitHub stars](https://img.shields.io/github/stars/srinathdoggala-tech/Hand-Written-?style=social)](https://github.com/srinathdoggala-tech/Hand-Written-/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/srinathdoggala-tech/Hand-Written-?style=social)](https://github.com/srinathdoggala-tech/Hand-Written-/network/members)
[![GitHub issues](https://img.shields.io/github/issues/srinathdoggala-tech/Hand-Written-)](https://github.com/srinathdoggala-tech/Hand-Written-/issues)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

AssignMe is an open source web application that helps students complete their assignments by converting digital text into customizable handwritten-style documents. The application provides two main features: generating handwritten-style documents from text and creating custom handwriting fonts from your own handwriting samples.

<img width="1923" height="897" alt="Screenshot" src="https://github.com/user-attachments/assets/14a7b827-ea74-4983-ac2d-7bbf28c5d5ad" />

<img width="1923" height="875" alt="Screenshot" src="https://github.com/user-attachments/assets/8e6649c0-dec6-4df4-bd86-e721801dfa80" />

## 🛡️ Open Source

This project is open source and released under the [MIT License](./LICENSE). You are free to use, modify, and distribute this software. Contributions are welcome!

## 🌟 Features

### 1. Assignment Text to Handwriting Converter

- Upload assignment questions (PDF or image)
- Enter subject name for better processing
- Customize handwriting style with various font options
- Adjust text parameters (font size, spacing, position)
- Apply different paper effects (shadows, scanner look)
- Choose pen color (blue, black, red, green)
- Generate and download handwritten documents as images or PDF

### 2. Custom Handwriting Font Generator

- Create your own handwriting font
- Capture handwriting samples from camera or uploaded images
- Follow guidelines for best results
- Use your custom font in the handwriting generator

### 3. AI-Powered Q&A System

- Text extraction from uploaded PDFs/images using Google Gemini
- Uses Gemini to draft answers to the assignment questions
- Runs as a separate FastAPI backend service

### 4. Advanced Font Processing Backend

- Server-side FontForge integration for professional font generation
- Dockerized backend service for scalable font processing
- High-quality font rendering and optimization

## 🖼️ System Architecture

![System Architecture](Assignment-main/public/images/Systemdesign.jpeg)

The application is a static front end (HTML/CSS/JS) that runs in the browser. Optional Python backends (Gemini Q&A and FontForge font generation) provide enhanced processing.

## 🚀 Getting Started

You can access the live version of the application at [assignme.live](https://assignme.live) or set up a local development environment following the instructions below.

### Prerequisites

- Modern web browser (Chrome, Firefox, Edge recommended)
- Internet connection
- For backend services: Docker (optional)
- Python 3.8+ (for AI services)

### Installation

1. Clone the repository:

   ```
   git clone https://github.com/srinathdoggala-tech/Hand-Written-.git
   ```

2. Navigate to the project directory:

   ```
   cd Hand-Written-
   ```

3. Open the application. It is a static site located in `Assignment-main/`:
   - Open `Assignment-main/index.html` in your browser, **or**
   - Serve the folder:

   ```
   cd Assignment-main
   python -m http.server 8000
   # then visit http://localhost:8000
   ```

### Backend Services Setup (Optional)

#### FontForge Backend Service

For custom font processing capabilities:

1. Navigate to the FontForge backend directory:

   ```
   cd Assignment-main/backend/fontforge
   ```

2. Build and run with Docker:

   ```
   docker build -t assignme-fontforge .
   docker run -p 8000:8000 assignme-fontforge
   ```

3. The FontForge backend will be available at `http://localhost:8000` (endpoint: `POST /generate-font`).

#### Gemini Q&A Service

For AI-powered question processing:

1. Navigate to the Q&A directory:

   ```
   cd Assignment-main/"q&a gemini"
   ```

2. Install dependencies:

   ```
   pip install -r requirements.txt
   ```

3. Set your Google Gemini API key as an environment variable (`GEMINI_API_KEY`).

4. Run the service:

   ```
   python main.py
   ```

**Note:** While this is a static web application that runs in the browser, the backend services provide enhanced functionality for font generation and AI processing.

## 📚 Usage

### Converting Text to Handwriting

1. Open the home page (`index.html`)
2. Upload your assignment question file (PDF/image)
3. Enter the subject name
4. Click "Upload" to process your assignment
5. Customize handwriting options (font, size, spacing, color)
6. Optionally upload a custom paper background image for different paper textures
7. Click "Generate Sheet" to create your handwritten document
8. Download the result as a PDF or individual images

### Creating Your Own Handwriting Font

1. Navigate to "Own Handwriting" section
2. Follow the capture guidelines (stay in the box, align with the grid, use black pen)
3. Either capture handwriting samples with your camera or upload images
4. Submit samples to generate your custom font
5. Use your new font in the main handwriting generator

## 🔧 Customization Options

### Handwriting Options

- **Font Selection**: Choose from a large set of handwriting styles
- **Font Size**: Adjust from small to large (up to 30pt)
- **Upload Custom Font**: Add your own TTF/OTF font files
- **Vertical Position**: Adjust text positioning on page
- **Word Spacing**: Control space between words
- **Letter Spacing**: Adjust space between letters
- **Effects**: Apply shadow, scanner, or no effect
- **Custom Paper Background**: Upload your own paper texture or background image
- **Pen Color**: Choose between blue, black, red, or green ink

## 📂 Project Structure

```
Hand-Written-/
├── server.js                 # Express server that serves Assignment-main/
├── package.json
├── README.md
├── LICENSE
├── .github/                 # Issue and PR templates
└── Assignment-main/         # The web application
    ├── index.html
    ├── docs.html
    ├── contactus.html
    ├── style.css
    ├── canvapage/
    │   ├── cypress.json
    │   ├── images/dropdown.svg
    │   └── js/
    │       ├── app.mjs
    │       ├── generate-images.mjs
    │       └── vendors/html2canvas.min.js
    ├── capture-image/
    │   ├── index.html
    │   ├── scripts.js
    │   └── style.css
    ├── public/
    │   ├── css/            # index.css, features.css
    │   ├── fonts/          # Handwriting .ttf fonts
    │   └── images/         # logo.png, Systemdesign.jpeg, docs/, ...
    ├── q&a gemini/         # Gemini Q&A backend (FastAPI)
    │   ├── main.py
    │   └── requirements.txt
    ├── backend/fontforge/  # FontForge backend (FastAPI)
    │   ├── app.py
    │   └── Dockerfile
    ├── script/             # Sample assets and tests
    │   ├── package.json
    │   ├── test.js
    │   └── images/
    └── src/
        ├── js/             # config.js, script.js
        ├── tests/
        └── utils/          # draw.mjs, generate-utils.mjs, helpers.mjs
```

## 🏗️ Architecture Overview

### Frontend Components

- **Main Application**: Static HTML/CSS/JS application running in browser
- **Canvas Page**: Interactive handwriting generation interface
- **Capture Interface**: Handwriting sample collection system

### Backend Services

- **FontForge Backend**: Dockerized Python service using FontForge and potrace for font generation
- **Gemini Q&A Service**: Python service using Google's Gemini API for text extraction and answering
- **File Processing API**: Handles document upload and text extraction

### Key Features

- **Client-Side Processing**: Most rendering runs directly in the browser (HTML2Canvas + jsPDF)
- **Optional Backends**: Enhanced capabilities via the FontForge and Gemini services
- **Custom Fonts**: Upload your own TTF/OTF or generate one from samples

## 🔄 API Integration

The application can integrate with backend services for enhanced processing.

### Main File Processing API

The upload flow in `index.html` posts to a hosted processing endpoint:

```javascript
const url = "https://test2-sfwm.onrender.com/process-file/";

function uploadFile() {
  const formData = new FormData();
  formData.append("file", file);
  formData.append("subject", subject);

  axios.post(url, formData, {
    headers: { 'Content-Type': 'multipart/form-data' },
  })
    .then(function (response) {
      // Display the processed response
    })
    .catch(function (error) {
      console.error("Error:", error);
    });
}
```

### FontForge Backend API

Runs locally when the Docker service is started:

```javascript
// Local FontForge backend (Docker)
const fontForgeUrl = "http://localhost:8000/generate-font/";

// POST handwriting sample images to generate a TTF font
```

### Gemini Q&A API

Runs locally when the Gemini service is started:

```javascript
// Local Gemini backend (FastAPI)
const geminiUrl = "http://localhost:8000/process-file/";

// POST a PDF/image with a subject to extract text and draft answers
```

> **Note:** The hosted endpoints above are for testing and demonstration purposes only. For local use, run the backends and point the front end at `localhost`.

## 🐳 Docker Deployment

### FontForge Backend

```bash
# Build the FontForge service
cd Assignment-main/backend/fontforge
docker build -t assignme-fontforge .

# Run the service
docker run -d -p 8000:8000 --name fontforge-service assignme-fontforge
```

## 🤖 AI Features

### Gemini Integration

The Q&A Gemini service provides:

- **Text Extraction**: Reads text from uploaded images and PDFs
- **Answer Drafting**: Uses Gemini to answer the extracted assignment questions
- **Subject Context**: Uses the provided subject name to frame the request

### Setup Requirements

1. A Google Gemini API key
2. Python 3.8+
3. Required dependencies (see `Assignment-main/q&a gemini/requirements.txt`)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Areas

- **Frontend Enhancements**: Improve UI/UX and add new features
- **Backend Services**: Enhance AI processing and font generation
- **API Integration**: Develop new backend service integrations
- **Documentation**: Improve guides and examples

## 📝 License

This project is available under the MIT License. See the LICENSE file for more information.

## 👥 Acknowledgments

- **HTML2Canvas** for converting HTML to images
- **jsPDF** for PDF generation
- **FontForge** and **potrace** for font generation
- **Google Gemini** for AI text extraction and answering
- **FastAPI** and **Docker** for the backend services
- **PyMuPDF** and **Pillow** for document/image handling
