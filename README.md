# QR Code Generator

This repository provides a simple Python script to generate a QR code with custom colors and error correction levels. The QR code in this example encodes a URL and saves the image to a file.

## Features

- Generates a QR code for a given URL
- Customizable QR code colors
- High error correction level
- Saves the QR code as an image file

## Prerequisites

- Python 3.x
- `qrcode` library
- `Pillow` library

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/qrcode-generator.git
    cd qrcode-generator
    ```

2. Install the required libraries:
    ```bash
    pip install qrcode[pil]
    ```

## Usage

1. Open the `generate_qr.py` file and customize the URL or data you want to encode in the QR code:
    ```python
    qr.add_data("https://www.linkedin.com/in/parth-gohil-3902a7256/")
    ```

2. Run the script:
    ```bash
    python generate_qr.py
    ```

3. The QR code image will be saved as `New_QRCode.png` in the current directory.

## Example Script

```python
import qrcode
from PIL import Image
import qrcode.constants

qr = qrcode.QRCode(
    version=1,
    error_correction=qrcode.constants.ERROR_CORRECT_H,
    box_size=10,
    border=4
)

qr.add_data("https://www.linkedin.com/in/parth-gohil-3902a7256/")
qr.make(fit=True)

img = qr.make_image(fill_color="dodgerblue", back_color="yellow")
img.save("New_QRCode.png")
```

## Customization

- **URL/Data**: Change the URL or the data in the `qr.add_data()` function to customize the content of the QR code.
- **Colors**: Modify the `fill_color` and `back_color` parameters in the `qr.make_image()` function to change the colors of the QR code.
- **Error Correction**: Adjust the `error_correction` parameter in the `QRCode` constructor to change the error correction level. Available levels are:
  - `qrcode.constants.ERROR_CORRECT_L` (7%)
  - `qrcode.constants.ERROR_CORRECT_M` (15%)
  - `qrcode.constants.ERROR_CORRECT_Q` (25%)
  - `qrcode.constants.ERROR_CORRECT_H` (30%)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contact

For any inquiries, please contact [Parth Gohil](https://www.linkedin.com/in/parth-gohil-3902a7256/).
