# Chatbot

import random

# Local data dictionary for quick responses
local_data = {
    "hello": "Hi there! How can I help you today?",
    "bye": "Goodbye! Have a great day!",
    "how are you": "I'm just a bot, but I'm doing well. Thanks for asking!",
    "what is your name": "I am a chatbot, created to assist you!",
    "help": "I am here to help you. What can I do for you?"
}

# List of fallback responses for when query isn't found in local data
fallback_responses = [
    "I'm not sure about that. Could you rephrase your question?",
    "Sorry, I don't have information on that topic. Can you ask something else?",
    "Hmm, I don't know the answer to that. Can you try another question?",
    "I didn't quite get that. Can you clarify?"
]

def get_local_response(query):
    """Returns a response based on local data or None if not found"""
    return local_data.get(query.lower())

def get_fallback_response():
    """Returns a fallback response from a predefined list"""
    return random.choice(fallback_responses)

def chatbot():
    """Main chatbot loop"""
    print("Chatbot: Hello! Ask me anything or type 'bye' to exit.")
    
    while True:
        user_input = input("You: ")
        
        if user_input.lower() == "bye":
            print("Chatbot: Goodbye!")
            break
        
        # Check if the input is in the local data
        response = get_local_response(user_input)
        
        if response:
            print("Chatbot:", response)
        else:
            # If not found locally, provide a fallback response
            print("Chatbot:", get_fallback_response())

if __name__ == "__main__":
    chatbot()
