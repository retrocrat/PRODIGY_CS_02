# Pixel Manipulation

### Project Overview

This tool leverages the Python Imaging Library (PIL) and NumPy to encrypt images by manipulating their pixels. By performing an XOR bitwise operation on each pixel value with a randomly generated key, the tool securely encrypts the image. Using the same key, it then decrypts the image back to its original form, ensuring the process is both effective and reversible.
Key Features

1. Image Encryption: Encrypts an image by applying an XOR operation on each pixel using a unique key.

2. Image Decryption: Reverses the encryption process to restore the original image, using the same key.

3. Random Key Generation: Generates a new random key for each encryption session, boosting security.

4. Simple Interface: Command-line interface for straightforward interaction, allowing users to specify the image file path easily.

### Technologies Used

Python: Core programming language for implementing encryption and decryption algorithms.
PIL (Python Imaging Library): Used for handling image loading and saving.
NumPy: Enables efficient manipulation of pixel data using arrays.

### Prerequisites

Ensure Python is installed, along with these required libraries:

PIL (Pillow)
NumPy

### Learning Outcomes

Through this project, I’ve gained valuable experience in implementing cryptographic principles using Python. It provided hands-on exposure to image processing, encryption, and the significance of data security in digital communications.

### Conclusion

This project serves as an engaging introduction to image encryption techniques in Python. It underscores the importance of encryption in safeguarding sensitive data and demonstrates how simple algorithms can be applied to enhance data security effectively.

### Code

Here is the Python code for the Pixel Manipulation:

```
from PIL import Image
import numpy as np

def load_image(image_path):
    """Load an image and return it as a NumPy array."""
    img = Image.open(image_path)
    return np.array(img)

def save_image(array, output_path):
    """Save a NumPy array as an image."""
    img = Image.fromarray(array)
    img.save(output_path)

def generate_key(shape):
    """Generate a random key with the specified shape."""
    return np.random.randint(0, 256, size=shape, dtype=np.uint8)

def xor_image(array, key):
    """Apply XOR operation on the image array using the key."""
    key_resized = np.resize(key, array.shape)
    return np.bitwise_xor(array, key_resized)

def encrypt_image(image_path, key_path="encrypted_image.png"):
    """Encrypt an image and save the encrypted image."""
    img_array = load_image(image_path)
    key = generate_key(img_array.shape)
    encrypted_array = xor_image(img_array, key)
    save_image(encrypted_array, key_path)
    print(f"Image encrypted successfully and saved as {key_path}.")
    return key

def decrypt_image(encrypted_image_path, key, output_path="decrypted_image.png"):
    """Decrypt an encrypted image and save the decrypted image."""
    encrypted_array = load_image(encrypted_image_path)
    decrypted_array = xor_image(encrypted_array, key)
    save_image(decrypted_array, output_path)
    print(f"Image decrypted successfully and saved as {output_path}.")

def main():
    print("Image Encryption and Decryption using Pixel Manipulation")

    # Get the image path from the user
    image_path = input("Enter the path to the image file: ")

    # Encrypt the image
    key = encrypt_image(image_path)

    # Decrypt the image
    decrypt_image("encrypted_image.png", key)

if __name__ == "__main__":
    main()
```


