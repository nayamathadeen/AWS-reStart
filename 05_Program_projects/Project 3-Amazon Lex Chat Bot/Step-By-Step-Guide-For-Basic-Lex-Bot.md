# Step-by-Step Guide: Part 1 – Creating a Basic Amazon Lex Bot

## Step 1: Log in to the AWS Management Console
- Open a web browser and go to **https://aws.amazon.com**
- Click **Sign In to the Console**
- Enter your AWS account credentials
- Once logged in, you will see the AWS Management Console dashboard

---

## Step 2: Select a Supported AWS Region
- In the top-right corner of the console, click the **Region selector**
- Choose a region that supports Amazon Lex, such as:
  - **EU (Ireland)**
  - **US East (N. Virginia)**
  
---

## Step 3: Open Amazon Lex
- Click the **search bar** at the top of the AWS console
- Type **Lex**
- Select **Amazon Lex** from the search results

You are now in the Amazon Lex V2 console.

---

## Step 4: Create a New Lex Bot
- Click **Create bot**
- Select **Create a blank bot**
- Click **Next** (if prompted)

---

## Step 5: Configure Bot Settings
- Enter a **Bot name** relevant to your project
- Set the **Language** to **English (ZA)**
- Leave all **advanced configuration options** set to **None**
- Click **Create** to create the bot

---

## Step 6: Create an Intent
- Inside your bot, click **Intents** in the left-hand menu
- Click **Create intent**
- Select **Create empty intent**
- Name the intent (for example, `S3Info`)
- Click **Add**

---

## Step 7: Add Sample Utterances
- In the intent editor, locate **Sample utterances**
- Add one or more utterances, such as:

What is Amazon S3?
Tell me about Amazon S3

- Press **Enter** after each utterance

Utterances define how users interact with the bot.

---

## Step 8: Add the Bot Response
- Scroll down to the **Opening response** section
- Click **Add response**
- Enter the response text:

Amazon S3 is a cloud storage service that lets you store and retrieve data from anywhere.

- Leave the **Closing response** empty

---

## Step 9: Save and Build the Bot
- Click **Save intent**
- Click **Build**
- Wait for the build process to complete

---

## Step 10: Test the Bot
- Open the **Test window** in the Amazon Lex console
- Type one of the sample utterances:

What is Amazon S3?

- Confirm that the bot responds correctly

---

## Final Outcome
- Created a functional Amazon Lex chatbot
- Successfully configured an intent, utterances, and responses
- Verified the bot’s behaviour using the test console
