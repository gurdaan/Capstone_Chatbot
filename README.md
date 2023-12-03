# Capstone_Chatbot
Executive Summary
The " ParkLink's Chatbot " project aimed to elevate customer engagement at Precise ParkLink's parking kiosks by implementing a sophisticated chatbot solution. Leveraging a comprehensive dataset of user-kiosk interactions, our approach involved the development of two key models.
The first model, an intent-based neural network, focused on answering common questions from Precise ParkLink's FAQ database. The second model, a generative transformer-based architecture, handled more open-ended inquiries and casual conversations.
Challenges were addressed, such as compatibility issues between TensorFlow versions for the two models. A solution was devised by creating a wrapper for the generative model, and deployment was streamlined using a Django API. The chatbot, seamlessly integrated into the parking kiosk system, now contributes to a more personalized and efficient user experience.
Looking forward, the project suggests potential enhancements for the chatbot, emphasizing the continuous evolution of this technology. Overall, this initiative represents a significant advancement for Precise ParkLink, showcasing the transformative power of leveraging historical data to enhance customer interactions.

1) We have used streamlit as our frontend
2) We have 2 models that are working in ensemble i.e. there is a threshold set so that if the first model does not give a good enough match for the question the second model comes in and gives a better answer.
   a) Intent Based model: This model works like a classification model. We have an intent file with a list of FAQ questions and answers for them. These are generic questions and problems that are most faced by customers. This model will answer all questions in the intent file and similar questions to those such as but not limited to "The machine is broken what do I do", "I lost my ticket what do I do", etc.
   b) Generative Model: This is a model that answers the general questions or prompts that the user will ask such as but not limited to "Hello how are you", "Who are you", "What does the company do" etc.

In the chatbot the first model will try to run first to try to answer the user's query, if the model does not have any similar question or if the trust level is very low then the second model will fire and answer the user's query.
Such an architecture is very useful because of multiple reasons:
  - Most asked questions are answered first hence the chatbot appears to be very fast.
  - The second model (which is very intensive and slow to run) will fire only if the first model does not fire.
  - Saves computational resources.
  - Gives better answers for frequently asked questions.
