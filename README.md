
# Chatbot Conversational Form
Chatbot Conversational Form is a demo project that simplifies creating interactive forms using a chatbot-style interface for tasks like surveys, questionnaires, and feedback forms.

## Features
- Collect User Information: The chatbot gathers user information in a natural and non-intrusive manner. It explains why it needs specific details from a predefined list.

- Empathetic Explanation: The chatbot kindly explains why it requests information, creating a user-friendly experience.

- Rapport Building: The chatbot engages in small talk to build rapport with users, maintaining a friendly atmosphere.

- Handling User Hesitation: The chatbot provides reassurance and alternatives if users hesitate, making corrections easy.

- Thankful and Supportive: When the task is complete, the chatbot expresses gratitude and offers further assistance.

- Conversation Workflow: The chatbot follows a clear and engaging conversation structure, avoiding list questions.

- Privacy and User-Centric: The chatbot prioritizes user comfort and data privacy.



## Tech Functionality
Used langchain's ConversationChain for chatbot and create_tagging_chain_pydantic for extract and validation of user input.


## Installation

To get started with Chatbot Conversational Form, you'll need Python 3.7+ installed. You can install the required dependencies using pip:

```bash
pip install -r requirements.txt
```

For Supporting memorization of user data, you need to use mongodb:
## Set up MongoDB to connect with Langchain
First you will configure a MongoDB database either locally or on the cloud. For this tutorial, we will use MongoDB Cloud, but if you prefer to set it up locally, you can follow the MongoDB installation instructions for your operating system.

Here’s a detailed description of setting up MongoDB Cloud:

1. Visit the MongoDB website and sign in to your account or create a new account if you don’t have one already.
2. Once you are logged in, navigate to the MongoDB Cloud or Atlas dashboard.
3. Click on the “Create a New Cluster” button to create a new MongoDB cluster. Choose the cloud provider and region that best suits your needs. You can follow the provided instructions and configuration options to set up your cluster.
4. Once your cluster is created and ready, go to the “Connect” section of your cluster.
5. Under the “Choose a connection method” screen, select “Connect your application.”
6. Select your preferred driver and version. MongoDB provides various drivers for different programming languages. Choose the one that matches the programming language you are using for your chatbot application.
7. In the “Connection String Only” tab, you will find the connection string. This string includes all the necessary information to connect your application to the MongoDB cluster, such as the server address, port number, database name, and credentials.
8. Click on the “Copy” button to copy the connection string to your clipboard.

This connection will allow us to store and retrieve chat history for session-based chat functionality.
Do not forget to replace your password in the connection string with your mongodb password.
Add connection string into in .env file as `MONGODB_URL` variable.

## Postgres: For Exisiting Customer Data
You can follow mongodb for storing data but here I took postgres DB.

Create table using below query:
```bash
CREATE TABLE customer2 (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255),
    city VARCHAR(255),
    email VARCHAR(255)
);
```
Provide your postgres connection variables in .env file as `DB_NAME`, `DB_USER`, `DB_PASSWORD`, `DB_HOST`, `DB_PORT` variables.


## Usage
Clone this repository to your local machine:
```bash
git clone https://github.com/abhishekshingadiya/chatbot_conversational_form.git
```

Navigate to the project directory:
```bash
cd chatbot_conversational_form
```

Run the main script to start the application:
```bash
streamlit run api.py 
```

Provide customer id as session id and gpt_token(OPENAI_API_KEY). 


![Screenshot 2023-11-06 at 12.29.05 PM.png](Screenshot%202023-11-06%20at%2012.29.05%E2%80%AFPM.png)
This data will store in mongodb (As Conversations History) and postgres DB (Add/update customer data).

![Screenshot 2023-11-06 at 12.34.26 PM.png](Screenshot%202023-11-06%20at%2012.34.26%E2%80%AFPM.png)

## Enhancement
- Introduce more details like age, contact_no in PersonalDetails class and map with customer table
- Introduce sentiment analysis to understand customer mood and based on that can change chatbot response.
- Support multiple language

## Contact

If you have any questions or suggestions, feel free to contact the project maintainer:

- Abhishek Shingadiya
- Email: abhishekshingadiya2543@email.com