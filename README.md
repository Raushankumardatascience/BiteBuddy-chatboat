# BiteBuddy-chatboat

🍔 Food Ordering Chatbot (FastAPI + Dialogflow + MySQL)
🧠 Overview

This is an intelligent food ordering chatbot backend built using FastAPI, Dialogflow, and MySQL.
It allows users to place, track, and manage their food orders using natural language through Dialogflow, while FastAPI handles the logic and database interaction.

⚙️ Tech Stack

🗣️ Dialogflow – for building and managing conversational flows (intents, entities, contexts).

⚡ FastAPI – backend server that processes webhook requests from Dialogflow.

🗄️ MySQL – to store order data and track statuses.

☁️ AWS (optional) – for hosting and deployment of the FastAPI backend.

🧩 Features

🍕 Add items to an order

🧾 Track order status by order ID

🔄 Maintain session context using Dialogflow

💬 Dynamic responses through webhook fulfillment

🗄️ Store and retrieve data via MySQL

🛠️ Setup Instructions
1. Clone the Repository
git clone https://github.com/your-username/food-chatbot.git
cd food-chatbot

2. Install Dependencies
pip install fastapi uvicorn mysql-connector-python

3. Set Up MySQL Database

Create a database and table for storing orders:

CREATE DATABASE food_chatbot;
USE food_chatbot;

CREATE TABLE orders (
  order_id INT AUTO_INCREMENT PRIMARY KEY,
  item_name VARCHAR(100),
  quantity INT,
  status VARCHAR(50)
);


Update your db_helper.py file with your local database credentials:

cnx = mysql.connector.connect(
    host="localhost",
    user="root",
    password="yourpassword",
    database="food_chatbot"
)

🚀 Running the Server

Run your FastAPI app locally:

uvicorn main:app --reload


This will start the backend on:
👉 http://127.0.0.1:8000/

🤖 Dialogflow Integration

Go to Dialogflow Console
.

Create your agent (or open an existing one).

Enable Fulfillment → paste your webhook URL (for example, if running locally with ngrok):

https://<your-ngrok-url>/


Enable webhook calls for intents like:

order.add - context: ongoing-order

track.order - context: ongoing-tracking

order.complete - context: ongoing-order

📦 Example Intents
Intent Name	Description
order.add - context: ongoing-order	Add new food items
track.order - context: ongoing-tracking	Check the current order status
order.complete - context: ongoing-order	Complete and confirm the order
☁️ Deployment (Optional)

Once tested locally, you can deploy the backend on:

AWS EC2

Render

Railway

Google Cloud Run

Vercel (for APIs)

💬 Author

Raushan Kumar
🎓 NIT Patna | Data Scientist & AI Developer
💼 Freelancer | Building intelligent systems for businesses
🚀 “Smart automation begins with smart code.”
