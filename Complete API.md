# 1) Generative AI Apps Overview

update readme!
## a) GPT-3 (OpenAI)
- **Functionality:** GPT-3 is a powerful language generation model
- **Features:** GPT-3 can be used for creative writing, chatbots
1) **Natural Language Understanding:** GPT-3 excels in understanding and generating human-like text across various topics and styles, thanks to its large-scale language model.

2) **Text Generation:** It can generate coherent and contextually relevant text, complete sentences, paragraphs, and even entire articles based on provided prompts.

3) **Language Translation:** GPT-3 can perform language translation tasks, converting text from one language to another with decent accuracy.

4) **Chatbot Capabilities:** It is capable of creating chatbots that engage in natural language conversations, providing responses based on the context of the conversation.

5) **Content Creation:** GPT-3 is often used for content creation purposes such as writing articles, product descriptions, marketing copy, and social media posts.

## b) DALL-E (OpenAI)
- **Functionality:** DALL-E is a generative model specifically designed
- **Features:** DALL-E is particularly useful for generating artwork
1) **Image Generation from Text:**  DALL-E is designed specifically for generating images based on textual descriptions or prompts, allowing users to describe images they want to see.

2) **Creative Artwork:** It can create unique and creative artwork based on abstract concepts or imaginative scenarios described in natural language.

3) **Customizable Image Outputs:** Users can specify various parameters such as style, composition, color palette, and more to customize the generated images.

4) **Visual Storytelling:** DALL-E can be used for visual storytelling, generating sequences of images that depict a narrative based on text input.

5) **Conceptual Understanding:** It demonstrates a high level of understanding of concepts and objects, enabling it to generate visually meaningful representations from textual descriptions.


 # 2) High-Level Architecture Design:
# a)  GPT-3 Architecture Design
![](./architecture.drawio.svg)
# b) DALL-E Architecture Design
![](./architecuredall.drawio.svg)


# 3) API Endpoints:

# a) GPT-3 API Endpoints

# i) Text Generation Endpoint
- Endpoint: `/api/gpt3/` text_generation
- Method: POST

Request Format:
```json
{
    "prompt": "Once upon a time",
    "max_tokens": 100,
    "temperature": 0.7
}
```
Response Format:
```json
{
    "generated_text": "Once upon a time, in a magical kingdom far away..."
}

```
- **Functionality:**
This endpoint generates text based on the provided prompt. Parameters like max_tokens control the length of the generated text, and temperature affects the randomness of the output.

# ii) Language Translation Endpoint
- Endpoint: `/api/gpt3/`language_translation
- Method: POST

Request Format:
```json
{
    "text": "Bonjour, comment ça va?",
    "target_language": "en"
}
```
Response Format:
```json
{
    "translated_text": "Hello, how are you?"
}
```
- **Functionality:**
This endpoint translates text from one language to another. The text parameter contains the text to be translated, and target_language specifies the language to translate into.


# b) DALL-E API Endpoints

# i) Image Generation Endpoint
- Endpoint: `/api/dalle/`image_generation
- Method: POST

Request Format:
```json
{
    "description": "a fluffy cat sitting on a moonlit window sill",
    "num_images": 1
}
```
Response Format:
```json
{
    "images": [
        {
            "url": "https://example.com/image_url/cat_on_window_sill.png",
            "description": "Generated image of a cat on a window sill"
        }
    ]
}
```
- Functionality:
This endpoint generates images based on textual descriptions. The description parameter describes the image, and num_images specifies the number of images to generate.

# ii) Image Style Transfer Endpoint
- Endpoint: `/api/dalle/`image_style_transfer
- Method: POST


Request Format:
```json
{
    "source_image_url": "https://example.com/source_image.jpg",
    "style_image_url": "https://example.com/style_image.jpg"
}
```
Response Format:
```json
{
    "styled_image_url": "https://example.com/styled_image.jpg"
}
```
- Functionality:
This endpoint performs style transfer on an input image using a style image. It takes the URLs of the source image and style image as input and returns the URL of the styled image.
 


