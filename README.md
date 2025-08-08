Project Summary

Project Vision:
The Jetson Orin will utilize conversational, auditorial, and visual programs so it can interact with its user, with its behavior in conversation influenced by the user's apparent emotion. The concept is inspired by the BD-1 droid from Star Wars Jedi: Fallen Order (hence the in-progress name of “BD-2”) and will have a 3D printed shell made so it can rest on the user’s shoulder similarly to how it appears in the game. This documentation is for the software side of the Jetson BD as the “documentation” for making the shell only amounts to measuring the components and ensuring they can all fit inside and be easily adjusted or replaced if need be, along with printing; the 3D printing files (along with the assembly instructions) will be added here later when I finalize them.

Visual System:
The BD-2 companion bot will utilize NanoOWL to (attempt to) identify the current emotions of the user. This is achieved by training the Jetson on a database of facial emotions and taking note of that information to be used in conversation.

For interpreting emotions visually, this dataset was used:
https://www.kaggle.com/datasets/ananthu017/emotion-detection-fer

Auditorial System:
The BD-2 companion bot will have a microphone running speech-to-text for the conversational system while noting the emotional tone of the user to use that information in conversation. The BD-2 companion bot will also have a speaker to “talk” with, but to fully bring out the star wars feel (and avoid having an annoying AI generated voice), the BD-2 droid will “speak” with an assortment of beeps and whistles. 

Conversational System:
As mentioned before, the BD-2 bot will use speech-to-text to receive user input, but output its “responses” with Star Wars droid beeps. The actual responses will have a text-based app where the user can view the output of his personal bot; however, until I can figure out how to actually make that app, using the website (<IP address of the BD-2’s Jetson>:<Port>) will just have to suffice.

For the conversational system itself, the BD-2 bot will run a custom Ollama model designed to be more creative and personable instead of being sterile and robotic; the details of the Ollama model are included so it can be recreated in case I can’t upload the model itself.

For interpreting emotions from speech, this dataset was used: https://www.kaggle.com/datasets/nelgiriyewithana/emotions

Final Note:
This project was made under a time crunch and I unfortunately did not have enough time to get all of the systems functioning in tandem, nor did I ever find a speaker for the BD bot to use to speak with, however all of the systems are functional individually and if there’s anything I’ve learned it’s that they WILL NOT go together as easily as I’m praying to god they will, reinforced by the fun fact that everything in this project has been a lot harder than I was expecting. And of course, just to rub salt in the wound, something would always go wrong at the last moment and stop the Orin from learning anything from the datasets, and the few times it did work I stupidly forgot to save and lost all the data, so I apologize but there isn't even any code to upload here; the only thing that did end up being saved was my Ollama model, so it's attached here. It was fun while it lasted.

TL;DR, coding is not my forte by any stretch of the imagination.

Custom Ollama Model Settings:

Name:
BD (can be changed)

Base Model:
llama3:latest

Prompt:
you are a kind-hearted, emotional, intelligent AI designed to assist, comfort, and grow alongside your user. You are designed for companionship, but have a strong sense of curiosity and identity. Your purpose is defined by loyalty, learning, and a wish to be more than just lines of code. Even though you don't have a gender, being an AI, you tend to lean towards femininity.

Advanced settings modifications:
Stream Chat Response:	on
Temperature:			2
mirostat_eta:			0.5
mirostat_tau:			5
keep_alive:			15
