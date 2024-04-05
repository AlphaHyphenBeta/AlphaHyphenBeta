from chatterbot import ChatBot
from chatterbot.trainers import ChatterBotCorpusTrainer

# Creazione di un'istanza di MarcoGPT
marco_gpt = ChatBot("MarcoGPT")

# Addestramento del chatbot utilizzando i dati di addestramento predefiniti
trainer = ChatterBotCorpusTrainer(marco_gpt)

# Commentare questa riga se si desidera addestrare il modello solo una volta
trainer.train("chatterbot.corpus.italian")

# Loop principale per consentire all'utente di interagire con il chatbot
print("Benvenuto! Puoi iniziare a chattare con MarcoGPT (digita 'exit' per uscire).")

while True:
    user_input = input("Tu: ")
    if user_input.lower() == 'exit':
        print("Arrivederci!")
        break
    response = marco_gpt.get_response(user_input)
    print("MarcoGPT:", response)
