# Full Stack AI Image Generator

#### Allows you to automatically generate image images from start to finish using AI. It will generate the text for the image (optionally based on a user-provided concept), create a related image, and combine the two into a final image file.
----------------------
<p align="center"><img src="https://a.ppy.sh/19637339?1687647975.jpeg" width=35%></p>

## Features

- Uses OpenAI's GPT-4 to generate the text and image prompt for the image.
- Automatically sends image prompt request to an AI image generator of choice, then combines the text and image
- Allows customization of the image generation process through various settings.
- Generates images with a user-provided subject or concept, or you can let the AI decide.
- Logs image generation details for future reference.

## Usage

1. For Python Version Only: Clone the repository & Install the necessary packages.
2. Obtain at least an OpenAI API key, but it is recommended to also use APIs from Clipdrop or Stability AI (DreamStudio) for the image generation stage.
3. Edit the settings variables in the settings.ini file.
4. Run the script and enter a image subject or concept when prompted (optional).

## Settings

Various settings for the image generation process can be customized:

- OpenAI API settings: Choose the text model and temperature for generating the image text and image prompt.
- Image platform settings: Choose the platform for generating the image image. Options include OpenAI's DALLE2, StabilityAI's DreamStudio, and ClipDrop.
- Basic image Instructions: You can tell the AI about the general style or qualities to apply to all images, such as using dark humor, surreal humor, wholesome, etc. 
- Special Image Instructions: You can tell the AI how to generate the image itself (more specifically,  how to write the image prompt). You can specify a style such as being a photograph, drawing, etc, or something more specific such as always using cats in the pictures.

## Example Image Output With Log
<p align="center"><img src="https://github.com/ThioJoe/Full-Stack-AI-Meme-Generator/assets/12518330/6400c973-f7af-45ed-a6ad-c062c2be0b64" width="400"></p>

```
image File Name: image_2023-07-13-15-34_ZYKCV.png
AI Basic Instructions: You will create funny images.
AI Special Image Instructions: The images should be photographic.
User Prompt: 'cats'
Chat Bot image Text: "When you finally find the perfect napping spot... on the laptop."
Chat Bot Image Prompt: "A photograph of a cat laying down on an open laptop."
Image Generation Platform: clipdrop
```

## Optional Arguments
### You can also pass options into the program via command-line arguments whether using the python version or exe version.

#### • API Key Arguments: Not necessary if the keys are already in api_keys.ini
`--openaikey`: OpenAI API key.

`--clipdropkey`: ClipDrop API key.

`--stabilitykey`: Stability AI API key.

#### • Basic image Arguments

`--userprompt`: A image subject or concept to send to the chat bot. If not specified, the user will be prompted to enter a subject or concept.

`--imagecount`: The number of images to create. If using arguments and not specified, the default is 1.

#### • Advanced image Settings Arguments

`--imageplatform`: The image platform to use. If using arguments and not specified, the default is 'clipdrop'. Possible options: 'openai', 'stability', 'clipdrop'.

`--temperature`: The temperature to use for the chat bot. If using arguments and not specified, the default is 1.0.

`--basicinstructions`: The basic instructions to use for the chat bot. If using arguments and not specified, the default is "You will create images that are good and original, and not cliche or lame.".

`--imagespecialinstructions`: The image special instructions to use for the chat bot. The default is "The images should be photographic.".

#### • Binary arguments: Just adding them activates them, no text needs to accompany them

`--nouserinput`: If specified, this will prevent any user input prompts, and will instead use default values or other arguments.

`--nofilesave`: If specified, the image will not be saved to a file, and only returned as virtual file part of imageResultsDictsList.
