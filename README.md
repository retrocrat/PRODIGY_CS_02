# Pixel Manipulation

### Project Overview

This tool leverages the Python Imaging Library (PIL) and NumPy to encrypt images by manipulating their pixels. By performing an XOR bitwise operation on each pixel value with a randomly generated key, the tool securely encrypts the image. Using the same key, it then decrypts the image back to its original form, ensuring the process is both effective and reversible.
Key Features

    "⋅" Image Encryption: Encrypts an image by applying an XOR operation on each pixel using a unique key.
    Image Decryption: Reverses the encryption process to restore the original image, using the same key.
    Random Key Generation: Generates a new random key for each encryption session, boosting security.
    Simple Interface: Command-line interface for straightforward interaction, allowing users to specify the image file path easily.

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


