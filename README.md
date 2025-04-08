# KukuVerse – Interactive Audio Stories

**KukuVerse** is a Streamlit web application that creates interactive, *choose-your-own-adventure* style audio stories using AI. The app generates story content, narrates it using text-to-speech, and lets users make choices that determine how the story unfolds.

---

## 🎯 Features

- 🧠 AI-generated interactive storytelling  
- 🔊 Text-to-speech narration (via gTTS)  
- 🌳 Branching narrative paths based on user choices  
- 🛠️ Customizable story settings:
  - Genre, protagonist, setting, and premise  
- 🔢 Option to set number of choices per decision point (2–4)

---

## 🔧 Prerequisites

- Python 3.6+
- Google AI Studio API key (for access to the Gemini AI model)

---

## 🚀 How to Use

1. Launch the app in Streamlit.
2. Enter your **Google AI Studio API key** in the sidebar.
3. Customize your story settings:
   - **Story Title**
   - **Genre**: Mystery, Adventure, Romance, Fantasy, Sci-Fi, Horror, Comedy
   - **Protagonist Description**
   - **Story Setting**
   - **Story Premise**
   - **Maximum Choices per Decision Point** (2 to 4)
4. Click **"Start New Story"**.
5. Read or listen to the story segment.
6. Select one of the choices to continue the story.
7. Continue making choices until you reach an ending.
8. Start a new story when you're done!

---

## 🧩 How It Works

### 🧱 Main Components

- **`StoryConfig`**: Stores user-defined story parameters.  
- **`StoryNode`**: Represents a segment of the story with content, choices, and audio.  
- **`NarrativeEngine`**: Generates story content using Google's Gemini AI.  
- **`TTSEngine`**: Converts story text to speech using gTTS.  
- **`KukuVerse`**: Coordinates overall flow of the app and story logic.

---

## 🔄 Application Flow

### 1. Setup Phase
- User enters API key and story settings.
- On clicking "Start New Story", settings are stored in session state.

### 2. Initialization Phase
- A new story opening is generated using `NarrativeEngine`.
- Audio is created for the story beginning using `TTSEngine`.
- Initial choices are generated for the player.

### 3. Gameplay Phase
- User is presented with the current story segment and choices.
- Selecting a choice triggers the next segment generation.
- Continues until an ending condition is met (typically after 3+ choices).

### 4. Ending Phase
- A story conclusion is generated.
- User can start a new story when done.

---

## 🧠 Story Generation Logic

- Each story segment is **250–300 words**, first-person narrative.
- 50% chance of story ending after 3+ choices.
- Story content is generated using **Gemini 2.0 Flash** model.
- Audio is created using **Google Text-to-Speech (gTTS)**.

---

## 💾 Session State Management

Streamlit's session state maintains:

- Story configuration
- Current node and history
- All generated story nodes (content, choices, audio)
- User's decision history

---

## 🧪 Sample Story

A built-in sample story **"The Venture Gamble"** is included.

> It follows an ambitious tech entrepreneur willing to risk everything for their startup dream.

## 🏁 Sample Walkthrough
- 📝 Fill in story settings  
  
![Filling all entries](https://github.com/user-attachments/assets/48a4ec63-c31f-4807-b13d-56eb49ad528c)

- ▶️ Story starts  
  
![Story starting](https://github.com/user-attachments/assets/03f0798f-9949-4b8b-8798-b378a059ce0a)

- 👉 Select an option  
  
![Selecting Option](https://github.com/user-attachments/assets/846090d2-ae2e-4bcd-a037-b9b7e4bb062d)

- 🧠 Next part of story generated  
  
![Processing next option](https://github.com/user-attachments/assets/89bef92a-bafd-45cf-8580-ba6ca8c51c89)

- 🔁 Repeat until story ends  
  
![Next Part of story after selecting option](https://github.com/user-attachments/assets/cb03f3c4-0f63-457c-b7fb-1172135a4ba1)

- As Continues….

---









---

## 📌 Conclusion

**KukuVerse** demonstrates the power of combining AI, text-to-speech, and interactive storytelling to deliver a unique narrative experience. Its modular design makes it easy to understand, extend, and personalize.

Happy story-building! 🎙️📚✨
