# CodeAlpha_Basicchatbot
import nltk
from nltk.chat.util import Chat, reflections
pairs = [
    (r"my name is (.*)", ("Hello %1, how can I help you today?", "Hi %1, what can I do for you?")),
    (r"what is your name?", ("You can call me Chatbot.", "I'm Chatbot, nice to meet you!")),
    (r"how are you?", ("I'm doing well, thank you!", "I'm fine, thanks for asking.")),
    (r"(.*) (good|great|fine|ok|well)", ("That's good to hear!", "Awesome!")),
    (r"(.*) (sorry|apologies)", ("No problem, don't worry about it.", "It's okay, no need to apologize.")),
    (r"quit", ("Goodbye!", "Bye!")),
]
chatbot = Chat(pairs, reflections)
def chatbot_interact():
    print("Hello! I'm a chatbot. Type 'quit' to exit.")
    while True:
        user_input = input("You: ")
        response = chatbot.respond(user_input)
        print("Chatbot:", response)
        if user_input.lower() == "quit":
            break
chatbot_interact()
