# Chatbot using Python

This repository contains a Python-based chatbot implementation. The chatbot leverages Natural Language Processing (NLP) techniques and machine learning models to provide a conversational interface. The project uses a Keras model trained on a set of intents and responses defined in a JSON file to understand and respond to user inputs.

## Files and Directories

- `chatbot_model.h5`: The trained Keras model's weights.
- `chatbot_model.json`: The architecture of the Keras model.
- `chatgui.py`: The main script to launch the chatbot GUI using Tkinter.
- `checkKrs.py`: A utility script (its specific use is to be determined based on the code content).
- `classes.pkl`: Serialized classes file containing the different intent classes.
- `intents.json`: JSON file defining the intents, patterns, and responses.
- `train_chatbot.py`: Script to preprocess data and train the chatbot model.
- `words.pkl`: Serialized words file containing the vocabulary.

## Installation and Setup

1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/your-username/Chatbot-using-Python.git
   cd Chatbot-using-Python
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Ensure you have NLTK data downloaded:
   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('wordnet')
   ```

4. Run the `train_chatbot.py` script to train the model:
   ```bash
   python train_chatbot.py
   ```

5. Start the chatbot GUI:
   ```bash
   python chatgui.py
   ```

## Training the Chatbot

The `train_chatbot.py` script handles the data preprocessing and model training:

1. **Data Preprocessing**:
   - Tokenizes and lemmatizes the patterns from `intents.json`.
   - Creates a bag of words model and labels for training.

2. **Model Training**:
   - Defines a Sequential model with Dense, Dropout, and SGD layers.
   - Trains the model on the preprocessed data and saves the weights to `chatbot_model.h5`.

## Using the Chatbot

The chatbot can be interacted with via the Tkinter GUI provided in `chatgui.py`. It allows users to type messages and receive responses based on the trained model. The interface includes:

- A chat log to display conversation history.
- An entry box for user input.
- A send button to submit messages.

## Intent and Response Structure

The `intents.json` file defines the chatbot's knowledge base. It includes:

- **tag**: A label for the intent.
- **patterns**: Example phrases that map to the intent.
- **responses**: Potential responses the chatbot can give.
- **context**: Contextual information to maintain conversation flow.

Example:
```json
{
    "intents": [
        {
            "tag": "greeting",
            "patterns": ["Hi there", "How are you", "Is anyone there?", "Hey", "Hola", "Hello", "Good day"],
            "responses": ["Hello, thanks for asking", "Good to see you again", "Hi there, how can I help?"],
            "context": [""]
        },
        ...
    ]
}
```

## Contributing

Contributions are welcome! If you have any suggestions, bug fixes, or new features to add, feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

---

Feel free to customize this README further to better suit the specifics of your project and your GitHub repository.
