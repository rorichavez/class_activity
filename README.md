# Image Captioning Project
This project uses the Salesforce model for image captioning utilizing the `transformers` library by Hugging Face. Below are the steps necessary for installing dependencies and using the model.
## Installation
1. First, ensure you have the required libraries installed. You can do this by running the following commands:
    ```bash
    !pip install -q transformers
    !pip3 install torch torchvision torchaudio
    ```
## Using the Salesforce Model
2. Use a pipeline as a high-level helper for image captioning. Here is an example of how to do this:
    ```python
    from transformers import pipeline
    # Initialize the pipeline for image captioning
    pipe = pipeline(“image-to-text”, model=“Salesforce/blip-image-captioning-large”)
    ```
3. Next, here is how to load an image from a URL and generate a caption for it:
    ```python
    from PIL import Image
    import requests
    # URL of the example image
    url = “http://images.cocodataset.org/val2017/000000039769.jpg”
    image = Image.open(requests.get(url, stream=True).raw)
    # Generate a caption for the image
    description = pipe(image)
    print(description)
    ```
## Complete Example
Here is the complete code for reference:
    ```python
    # Installing the required libraries
    !pip install -q transformers
    !pip3 install torch torchvision torchaudio
    # Importing the libraries
    from transformers import pipeline
    from PIL import Image
    import requests
    # Initialize the pipeline for image captioning
    pipe = pipeline(“image-to-text”, model=“Salesforce/blip-image-captioning-large”)
    # URL of the example image
    url = “http://images.cocodataset.org/val2017/000000039769.jpg”
    image = Image.open(requests.get(url, stream=True).raw)
    # Generate a caption for the image
    description = pipe(image)
    print(description)
    ```
