Photo or Text to 3D Model
Generator
Overview
This project is a prototype that accepts either a 2D image (JPEG/PNG) or a
natural language prompt (e.g., “A small toy car”) as input, and outputs a
basic 3D visualization of the subject using displacement mapping. It
includes functionality for background removal, image generation via
Stability AI, and an interactive Three.js-based viewer.
The goal is to simulate a lightweight, accessible pipeline for producing a 3D
mesh from minimal user input—either a photograph or a short descriptive
prompt—demonstrating AI-assisted generation with simplified geometry.
Features
Photo-to-3D: Accepts a photo of a single object (with transparent or
removable background), processes it, and creates a basic 3D
representation.
Text-to-3D: Converts a text prompt into an image using Stability AI,
then applies the same image processing and 3D mapping pipeline.
Background Removal: Utilizes rembg to isolate the foreground object.
3D Viewer: Provides a browser-based 3D mesh viewer using Three.js,
including orbit controls and dynamic lighting.
Output Files: Saves all intermediate and final outputs (image and
HTML).
Setup Instructions
1. Clone the Repository
bash git clone https://github.com/yourusername/photo-textto-3d.git cd photo-text-to-3d
2. Set Up a Virtual Environment
bash python3 -m venv venv source venv/bin/activate # On Windows:
venv\Scripts\activate
3. Install Required Packages
bash pip install -r requirements.txt
•
•
•
•
•
Requirements
requirements.txt should contain:
numpy pillow rembg onnxruntime requests ipython matplotlib tqdm
How to Run
Run the main script:
bash python main.py
When prompted:
Enter image to upload a photo or enter an image URL
Enter text to provide a descriptive prompt (e.g., "A miniature toy
robot")
The generated image (after background removal or AI synthesis) will be
saved, and a corresponding 3D viewer (index.html) will be created and
offered for download.
System Workflow
Image-to-3D Pipeline
Input image is loaded from local file or URL.
Background is removed using rembg.
A height map is generated from the image texture.
A 3D mesh is rendered using Three.js with displacement mapping.
Text-to-3D Pipeline
Stability AI API generates an image from a text prompt.
Background is removed and image processed as in the photo-based
pipeline.
API Key Configuration
The application requires a Stability AI API key for text-to-image
functionality.
Update this line in the script with your key:
python self.stability_api_key = "sk-xxxxxx..."
Sign up for a key at: https://platform.stability.ai
.
.
.
.
Example Prompts
“A classic red convertible toy car”
“A medieval throne made of stone”
“A small wooden stool with curved legs”
Output Files
output/generated_image.png: AI-generated image (text mode)
output/original_image.png: Processed input image (background
removed)
output/index.html: Interactive 3D visualization
(Optional future extension: Export to .obj or .stl formats)
Notes
This project serves as a lightweight demonstration of 2D-to-3D concepting
using common Python tools and web rendering techniques. It is built with
portability and accessibility in mind and is suitable for prototyping,
educational use, or rapid visualization in a browser.
