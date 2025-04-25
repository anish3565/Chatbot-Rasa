# 🤖 Chatbot with Rasa Framework

An intelligent conversational agent built using the Rasa framework, designed to handle customer queries and provide assistance in a natural, conversational manner.

## 📋 Project Overview

This project demonstrates the implementation of a conversational AI chatbot using the Rasa open-source framework. The chatbot is designed to understand user intent, maintain context across conversations, and provide appropriate responses to user queries. It can handle multiple conversation flows, recognize entities, and respond with relevant information.

## 🔍 Repository Structure

```
Chatbot-Rasa/
├── actions/                 # Custom action code
│   └── actions.py           # Python code for custom actions
├── config/                  # Configuration files
├── data/                    # Training data
│   ├── nlu.yml              # NLU training examples
│   └── stories.yml          # Conversation flows
├── domain.yml               # Bot's domain (intents, entities, responses)
├── endpoints.yml            # Endpoints configuration
├── config.yml               # Model configuration
├── credentials.yml          # Connection credentials
└── tests/                   # Testing files
```

## 🌟 Features

- **Natural Language Understanding**: Processes and understands user messages
- **Contextual Conversations**: Maintains context throughout user interactions
- **Intent Recognition**: Identifies the purpose behind user messages
- **Entity Extraction**: Extracts important information from user inputs
- **Custom Actions**: Executes specific actions in response to user requests
- **Multiple Conversation Paths**: Handles various conversation flows seamlessly

## 🛠️ Technologies & Tools

- [Rasa](https://rasa.com/) (Version 3.x)
- Python 3.7+
- TensorFlow
- spaCy
- Docker (optional for deployment)

## 🚀 Getting Started

### Prerequisites

- Python 3.7 or higher
- pip (Python package manager)
- Virtual environment tool (recommended)

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/anish3565/Chatbot-Rasa.git
cd Chatbot-Rasa
```

2. **Create and activate a virtual environment:**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install Rasa and dependencies:**
```bash
pip install -r requirements.txt
```

### Training the Model

Train the Rasa model with the following command:

```bash
rasa train
```

This will create a trained model in the `models/` directory.

### Running the Chatbot

1. **Start the Rasa server:**
```bash
rasa run
```

2. **In a separate terminal, start the actions server:**
```bash
rasa run actions
```

3. **To interact with the bot in your terminal:**
```bash
rasa shell
```

## 💬 Example Conversations

```
User: Hello
Bot: Hi there! How can I help you today?

User: I need information about your product pricing
Bot: I'd be happy to help with pricing information. Which product are you interested in?

User: The premium plan
Bot: Our premium plan is $49.99 per month and includes all features plus priority support.
     Would you like to know more about the features?
```

## 🔧 Customization

### Adding New Intents

1. Add training examples in `data/nlu.yml`:
```yaml
- intent: ask_business_hours
  examples: |
    - What are your business hours?
    - When are you open?
    - What time do you close?
```

2. Define responses in `domain.yml`:
```yaml
responses:
  utter_business_hours:
    - text: "We're open Monday to Friday, 9 AM to 5 PM."
```

3. Add to conversation flows in `data/stories.yml`

### Creating Custom Actions

1. Define the action in `domain.yml`
2. Implement the action in `actions/actions.py`
3. Include the action in your stories

## 📊 Performance & Evaluation

The chatbot model can be evaluated using Rasa's built-in evaluation tools:

```bash
rasa test nlu --nlu data/nlu.yml
rasa test core --stories data/stories.yml
```

## 🔄 Continuous Improvement

- Regularly update training data based on conversation logs
- Refine responses based on user feedback
- Add more intents and entities as needed
- Optimize model parameters for better understanding

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📬 Contact

For questions, feedback, or collaboration opportunities, please contact Anish through GitHub.

## 🔗 Resources

- [Rasa Documentation](https://rasa.com/docs/)
- [Rasa Community Forum](https://forum.rasa.com/)
- [Rasa GitHub](https://github.com/RasaHQ/rasa)
