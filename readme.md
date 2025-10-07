# Image Anonymizer

This project uses the Gemini API to anonymize images by removing or blurring numeric values, quantities, and prices.

## Installation

1.  Clone the repository.
2.  Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

1.  Place your images (PNG, JPG, JPEG) in the `input_images` directory.
2.  Run the main script:
    ```bash
    python main.py
    ```
3.  The anonymized images will be saved in the `output_images` directory.

## Configuration

Before running the script, you need to set up your Gemini API key. Open `utils/image_utils.py` and replace `"YOUR_API_KEY"` with your actual API key.
