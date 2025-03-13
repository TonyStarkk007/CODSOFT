# CODSOFT
# Simple Python Chatbot Implementation Using If-Else:
def chatbot_response(user_input):
    user_input = user_input.lower()
   
   if "hello" in user_input or "hi" in user_input or "hey" in user_input:
        return "Hello! How can I assist you today?"
    
   elif "how are you" in user_input:
        return "I'm just a chatbot, but I'm doing well! How can I help you?"

   elif "weather" in user_input or "forecast" in user_input:
        return "I don't have access to real-time weather data, but you can check your local weather app!"

   elif "goodbye" in user_input or "bye" in user_input or "see you" in user_input:
        return "Goodbye! It was nice chatting with you. Have a great day!"

   elif "your name" in user_input or "who are you" in user_input:
        return "I am a simple chatbot created to assist you with basic queries."

   else:
        return "I'm sorry, I didn't understand that. Could you rephrase your question?"

def chat():
    print("Chatbot: Hello! I'm a simple chatbot. Type 'exit' to end the conversation.")

   while True:
        user_input = input("You: ")
        if user_input.lower() == "exit":
            print("Chatbot: Goodbye! It was nice talking to you.")
            break
        response = chatbot_response(user_input)
        print(f"Chatbot: {response}")

chat()


![IMG-20250313-WA0006](https://github.com/user-attachments/assets/3712014a-d637-4dd2-9269-215a48728be9)
![IMG-20250313-WA0007](https://github.com/user-attachments/assets/42ec4e71-a262-4c9a-8eb3-17244e99e763)
