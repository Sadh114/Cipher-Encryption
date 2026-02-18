Live deployed Website : https://cipher-encryption-1.onrender.com

# AES Image Encryption: ECB vs CBC

An interactive full-stack web app that demonstrates how AES encryption behaves in **ECB** and **CBC** modes using real image data.

Users can upload an image, process it through the backend, and visually compare:
- Original image
- ECB encrypted image
- CBC encrypted image
- Decrypted outputs

## Why this project exists

This project is built for learning cryptography visually.  
It helps show why ECB is insecure for structured data (pattern leakage) and why CBC is better for confidentiality.

## Features

- Image upload from browser
- Server-side AES encryption/decryption
- Side-by-side visual comparison
- Clean React UI with explanation sections
- Render-ready deployment setup (frontend + backend)

## Tech Stack

### Frontend
- React + TypeScript
- Vite
- Tailwind CSS
- shadcn/ui components

### Backend
- Python Flask
- PyCryptodome (AES)
- Pillow (image handling)
- NumPy (pixel/byte conversion)
- Flask-CORS
- Gunicorn (production server)

## Project Structure

```txt
.
├── src/                     # React frontend source
│   ├── pages/Index.tsx      # Main workflow (upload + process call)
│   └── components/          # UI sections and reusable components
├── public/                  # Static assets (favicon, etc.)
├── backend/
│   ├── app.py               # Flask API
│   ├── requirements.txt     # Python dependencies
│   ├── uploads/             # Uploaded images (runtime)
│   └── processed/           # Encrypted/decrypted results (runtime)
├── index.html
├── package.json
└── vite.config.ts
```

### How it works

- User uploads an image on frontend.

- Frontend sends multipart/form-data to backend /process.

### Backend:
  - Reads image bytes (RGB)
  - Generates AES key
  - Encrypts bytes with ECB and CBC
  - Decrypts both for verification
  - Saves generated images
    
- Backend returns image paths in JSON.

- Frontend displays all outputs for comparison.
