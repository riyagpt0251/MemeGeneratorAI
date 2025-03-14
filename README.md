# Meme Generator README

![Meme Generator](https://media.giphy.com/media/xT9IgG50Fb7Mi0prBC/giphy.gif)

## 📌 Overview
This project is a simple **Meme Generator** that allows users to create their own memes by adding text to predefined meme templates. The script utilizes **Pillow** for image manipulation and **Transformers** for future enhancements like meme captioning.

---
## 🚀 Features
✅ Download popular meme templates
✅ Customize text on memes
✅ Supports multiple templates
✅ Automatically centers text with stroke effects
✅ Saves generated memes

---
## 📦 Installation
To get started, install the required dependencies:

```sh
pip install transformers pillow memegen
```

---
## 🔗 Dependencies
- **Pillow** (Image manipulation)
- **Transformers** (For potential AI-based meme text generation)
- **Memegen** (For additional templates)

---
## 📥 Download Meme Templates
Run the following commands to fetch meme templates:

```sh
wget https://i.imgflip.com/1bij.jpg -O distracted_boyfriend.jpg
wget https://i.imgflip.com/30b1gx.jpg -O drake_hotline_bling.jpg
wget https://i.imgflip.com/1g8my4.jpg -O two_buttons.jpg
```

---
## 🛠 Usage

### 1️⃣ Import Libraries
```python
from PIL import Image, ImageDraw, ImageFont
import os
```

### 2️⃣ Define Meme Templates
```python
MEME_TEMPLATES = {
    "distracted_boyfriend": "distracted_boyfriend.jpg",
    "drake_hotline_bling": "drake_hotline_bling.jpg",
    "two_buttons": "two_buttons.jpg",
}
```

### 3️⃣ Function to Generate Meme
```python
def create_meme(template_name, top_text, bottom_text=""):
    image = Image.open(MEME_TEMPLATES[template_name])
    draw = ImageDraw.Draw(image)
    
    # Load a font
    try:
        font = ImageFont.truetype("arial.ttf", 40)
    except IOError:
        font = ImageFont.load_default()
    
    # Add text
    draw.text((image.width // 2, 10), top_text, font=font, fill="white", anchor="mt", stroke_width=2, stroke_fill="black")
    draw.text((image.width // 2, image.height - 50), bottom_text, font=font, fill="white", anchor="mb", stroke_width=2, stroke_fill="black")
    
    return image
```

### 4️⃣ Generate a Meme
```python
template_name = "distracted_boyfriend"
top_text = "Me: Working on my project"
bottom_text = "Also me: Procrastinating on memes"

meme = create_meme(template_name, top_text, bottom_text)

display(meme)
meme.save("generated_meme.png")
print("Meme saved as 'generated_meme.png'")
```

---
## 🖼 Example Output

![Example Meme](generated_meme.png)

---
## 🎉 Contributing
Feel free to submit pull requests or suggest new meme templates!

---
## 📜 License
This project is **MIT Licensed**. Enjoy meme-making! 😆

