# Generative AI Chatbot with Memory

This repository provides a conversational AI chatbot interface built with **LangChain**, **Google Generative AI**, and **Gradio**. The chatbot retains conversation history and can recall details across multiple interactions within the same session. It demonstrates the use of memory in AI-driven conversations, allowing for context-aware responses based on prior exchanges.

## Features

- **Google Generative AI Integration**: The chatbot is powered by Google’s Generative AI, delivering high-quality responses.
- **Session Memory**: User-specific conversation history is preserved, enabling the bot to refer back to previous messages within a session.
- **Gradio Interface**: An interactive, user-friendly interface for real-time conversation, displaying both user queries and AI responses.
- **Dynamic Prompting**: The chatbot uses LangChain’s prompt templates to customize its conversational style.

## Requirements

- **Python 3.10+**
- **API Key for Google Generative AI**
- **LangChain, dotenv, and Gradio** libraries

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/vinodvpillai/generativeAI-chatbot-with-memory.git
   cd generativeAI-chatbot-with-memory
   ```

2. **Install dependencies**:
   ```bash
   pip install langchain langchain-google-genai gradio pydantic python-dotenv
   ```

3. **Set up environment variables**:
   - Create a `.env` file in the root directory and add your Google Generative AI API key and model configuration:

   ```plaintext
   GOOGLE_API_KEY=<your_google_api_key>
   GOOGLE_MODEL=<your_google_model>
   ```

## Usage

### Running the Chatbot

1. Start the chatbot by running the main script:

   ```bash
   python your_script.py
   ```

2. Open the Gradio interface in your browser (it will provide a link in the terminal).

3. **Chat with the Bot**:
   - Enter a username and a query in the provided fields.
   - Each query and response will be displayed in the chat history with labels `[username]` and `[AI]`.

### Example Chat Flow

- **Username**: `Vinod`
- **User Query 1**: "Hi, I would like to know a brief overview of AI."
- **Bot Response 1**: AI provides a brief description of artificial intelligence.
- **User Query 2**: "Do you remember my name?"
- **Bot Response 2**: "Yes, your name is Vinod."

The chatbot recalls prior messages, providing a seamless and contextually rich interaction.

## Code Overview

1. **Environment Setup**: Loads the `.env` file to get API credentials for Google Generative AI.
2. **Model and Prompt Initialization**: Sets up the Google Generative AI model and a conversational prompt template.
3. **Session Memory**: 
   - Manages conversation history with `InMemoryHistory`, a custom class to store message sequences.
   - Retrieves or creates new session histories as needed.
4. **Gradio Interface**:
   - Uses `gr.Chatbot` to display the chat history sequentially.
   - Displays each exchange with labels indicating whether it was the user's query or the bot's response.

## File Structure

```plaintext
.
├── main.py                # Main script to run the chatbot
├── README.md              # Documentation
├── .env                   # Environment variables file
└── requirements.txt       # Python dependencies
```

### Sample `.env` file

```plaintext
GOOGLE_API_KEY=your_google_api_key
GOOGLE_MODEL=your_google_model_name
```

## Dependencies

This project requires the following libraries:
- `langchain` - Core library for language model integration and prompt management.
- `gradio` - For creating a web-based chat interface.
- `pydantic` - Data validation and settings management.
- `python-dotenv` - Loads environment variables from a `.env` file.

Install dependencies using:
```bash
pip install -r requirements.txt
```

## Contributing

Feel free to submit issues or pull requests if you’d like to contribute to the project. Contributions are welcome to enhance functionality or improve the user interface.

## License

This project is licensed under the MIT License. See `LICENSE` for details.

## Acknowledgments

- [LangChain](https://github.com/hwchase17/langchain) for enabling robust prompt and memory management.
- [Gradio](https://github.com/gradio-app/gradio) for the intuitive and easy-to-use chat interface.
- [Google Generative AI](https://cloud.google.com/generative-ai) for powering high-quality conversational responses.
