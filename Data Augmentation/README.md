🛠️ Installation

!pip install Augmentor

📁 Setup

import Augmentor
p = Augmentor.Pipeline('/content/dog.jpg')  # Replace with your image path or folder

🔄 Image Rotation

# Random rotation left or right
p.rotate(probability=0.3, max_left_rotation=10, max_right_rotation=10)

# Rotate fixed angles
p.rotate90(probability=0.3)
p.rotate180(probability=0.3)
p.rotate270(probability=0.3)

# Rotate by random 90-degree increments
p.rotate_random_90(probability=0.3)

🔁 Flipping

# Horizontal and vertical flip
p.flip_left_right(probability=0.3)
p.flip_top_bottom(probability=0.3)

✂️ Random Cropping

p.crop_random(probability=0.1, percentage_area=0.5)

📐 Resize

p.resize(probability=0.1, width=100, height=100)

💡 Brightness Adjustment

p.random_brightness(probability=0.5, min_factor=0.4, max_factor=0.9)

🎨 Random Color

p.random_color(probability=0.5, min_factor=0.4, max_factor=0.9)

🖼️ Random Contrast

p.random_contrast(probability=0.5, min_factor=0.9, max_factor=1.4)

🔀 Elastic Distortion

p.random_distortion(probability=0.5, grid_width=7, grid_height=8, magnitude=9)

✅ Run Pipeline

p.sample(10)  # Generate 10 new images

📂 Output

Saved to: /content/dog.jpg/output/

🧼 Cleanup (Optional)

p.clear_transforms()

🧠 Pro Tips

- Set probability=1.0 to always apply an operation.
- Chain multiple augmentations for variety.
- Useful for CNNs, ViTs, autoencoders, etc.

🚀 Example Use Case

p.rotate(probability=0.5, max_left_rotation=5, max_right_rotation=5)
p.flip_left_right(probability=0.5)
p.random_brightness(probability=0.5, min_factor=0.5, max_factor=1.2)
p.sample(20)

👀 Preview Images (in Notebooks)

from IPython.display import Image
Image("/content/dog.jpg/output/0.jpg")
