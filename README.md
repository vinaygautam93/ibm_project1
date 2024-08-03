# ibm_project1
ai chat bot
from chatterbot import ChatBot
from chatterbot.trainers import ListTrainer

# Create a new chat bot named Charlie
chatbot = ChatBot('FreeBirdsBot')

trainer = ListTrainer(chatbot)

trainer.train(['Hi','Hello','How are you?','I am fine and You?','Greate','What are you Doing?','nothing just roaming around.'])

while True:
	input_data = input("You- ")
	response = chatbot.get_response(input_data)
	print("FreeBirdsBot- ",response)



 {"intents": [
        {"tag": "greeting",
         "patterns": ["Hi", "How are you", "Is anyone there?", "Hello", "Good day"],
         "responses": ["Hello, thanks for visiting", "Good to see you again", "Hi there, how can I help?"],
         "context_set": ""
        },
        {"tag": "goodbye",
         "patterns": ["Bye", "See you later", "Goodbye"],
         "responses": ["See you later, thanks for visiting", "Have a nice day", "Bye! Come back again soon."]
        },
        {"tag": "thanks",
         "patterns": ["Thanks", "Thank you", "That's helpful"],
         "responses": ["Happy to help!", "Any time!", "My pleasure"]
        },
        {"tag": "hours",
         "patterns": ["What hours are you open?", "What are your hours?", "When are you open?" ],
         "responses": ["We're open every day 9am-9pm", "Our hours are 9am-9pm every day"]
        },
        {"tag": "mopeds",
         "patterns": ["Which mopeds do you have?", "What kinds of mopeds are there?", "What do you rent?" ],
         "responses": ["We rent Yamaha, Piaggio and Vespa mopeds", "We have Piaggio, Vespa and Yamaha mopeds"]
        },
        {"tag": "payments",
         "patterns": ["Do you take credit cards?", "Do you accept Mastercard?", "Are you cash only?" ],
         "responses": ["We accept VISA, Mastercard and AMEX", "We accept most major credit cards"]
        },
        {"tag": "opentoday",
         "patterns": ["Are you open today?", "When do you open today?", "What are your hours today?"],
         "responses": ["We're open every day from 9am-9pm", "Our hours are 9am-9pm every day"]
        },
        {"tag": "rental",
         "patterns": ["Can we rent a moped?", "I'd like to rent a moped", "How does this work?" ],
         "responses": ["Are you looking to rent today or later this week?"],
         "context_set": "rentalday"
        },
        {"tag": "today",
         "patterns": ["today"],
         "responses": ["For rentals today please call 1-800-MYMOPED", "Same-day rentals please call 1-800-MYMOPED"],
         "context_filter": "rentalday"
        }
   ]
}



