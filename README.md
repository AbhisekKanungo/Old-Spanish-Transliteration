# Old-Spanish-Transliteration
Transliteration of text from centuries-old works presents a significant challenge in the field of text recognition. While modern tools excel at extracting text from contemporary, clearly printed sources, they fall short when applied to older forms of print or manuscripts. The historical value of these texts is immense, and successfully transcribing them can open new avenues for research and understanding of the period.

# Model Presentation
The TrOCR model architecture is based on the Transformer framework, comprising an image Transformer as the encoder and a text Transformer as the decoder.The encoder takes input images, decomposes them into patches, and processes them to obtain visual features. These features are then used by the decoder to generate wordpiece sequences in an autoregressive way, guided by the visual information and previous predictions.
This design allows TrOCR to leverage pre-trained models for image understanding and language modeling, resulting in state-of-the-art performances.
![Unknown](https://github.com/user-attachments/assets/d8eec902-e004-4bcc-a2d8-86d2e96ccf5c)
# Dataset
The Dataset involved scraping 131,000 random Wikipedia pages and extracting 2,000,000 samples, ranging from single-word instances to 10-word sentences.
Subsequently,images were generated artificially from these samples, applied various data augmentation techniques, and results were achieved as the following:
![Unknown](https://github.com/user-attachments/assets/231fdd71-c869-4c1a-a834-57df5d8d9fd6)
# Image Preprocessing and OCR text Recognition
The TrOCRProcessor and VisionEncoderDecoderModel are loaded from the qantev/trocr-large-spanish model. The processor handles preparing the image input, and the model performs the text generation based on the image.
The image is opened using the PIL library, converted to RGB (which is expected by the model), and passed to the processor to convert it into pixel values.
The model generates text from the pixel values. Then, the processor decodes the generated text by skipping special tokens, producing the final OCR result in Spanish.
