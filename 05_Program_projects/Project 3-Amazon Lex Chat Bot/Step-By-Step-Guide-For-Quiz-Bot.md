# Step-by-Step Guide: How I Built the Amazon Lex Quiz Chatbot (Part 2)

## Step 1: Access Amazon Lex
- Logged in to the AWS Management Console
- Selected a supported AWS Region (EU – Ireland or US East – N. Virginia)
- Used the search bar to find and open **Amazon Lex**

![AWS Console](assets/Step-1-AWS-Console.png)

---

## Step 2: Create the Amazon Lex Bot
- Clicked **Create bot**
- Selected **Create a blank bot**
- Named the bot appropriately for the project
- Set the language to **English (ZA)**
- Selected **None** for advanced configuration
- Clicked **Create** to provision the bot

---

## Step 3: Create the Quiz Intent
- Navigated to **Intents** within the bot
- Created a new empty intent named `S3Quiz`

![Quiz Intent Name](assets/Step-3-Quiz-Intent-Name.png)

- Added sample utterances:
  - `Start quiz`
  - `Quiz me on S3`
  - `I am ready for the quiz`

![Sample Utterance](assets/Step-3-Added-Sample-Utterance.png)

---

## Step 4: Add the Quiz Question
- Scrolled to the **Opening response** section of the `S3Quiz` intent
- Added the quiz question:
What does Amazon S3 stand for?

Answer A: Simple Storage Service
Answer B: Secure Server Storage
Answer C: Smart Storage System

Please type Answer A, Answer B, or Answer C.

![Adding Quiz Questions](assets/Step-4-Adding-Quiz-Questions.png)

- Left the **Closing response** empty so the bot waits for user input
- Saved the intent

---

## Step 5: Create the Correct Answer Intent
- Created a new empty intent named `CorrectAnswer`

![Creating correct answer](assets/Step-5-Creating-Correct-Answer.png)

- Added sample utterances:
- `Answer A`
- `Simple Storage Service`

![Sample utterance](assets/Step-5-Sample-Utterance.png)

- Added the initial response:
Correct!
Amazon S3 stands for Simple Storage Service.

![Initial response](assets/Step-5-Initial-response.png)

- Left the closing response empty
- Saved the intent

---

## Step 6: Create the Incorrect Answer Intent
- Created a new empty intent named `WrongAnswer`

![Creating name](assets/Step-6-Creating-Wrong-Answer.png)

- Added sample utterances:
- `Answer B`
- `Answer C`
- `Secure Server Storage`
- `Smart Storage System`

![Sample utterances](assets/Step-6-Sample-Utterances.png)

- Added the initial response:
Incorrect.
The correct answer is Simple Storage Service.

![Initial Response](assets/Step-6-Initial-Response.png)

- Left the closing response empty
- Saved the intent

---

## Step 7: Build the Bot
- Clicked **Build** after saving all intents
- Waited for the build process to complete

![Build the bot](assets/Step-7-Build-the-bot.png)

---

## Step 8: Test the Quiz
- Opened the **Test window** in Amazon Lex
- Typed `Start quiz` to begin
- Verified:
- `Answer A` returned the correct response
- `Answer B` or `Answer C` returned the incorrect response

![Testing](assets/Step-8-Testing.png)

---

## Step 9: (Optional) Add a Second Quiz Question
- Created a new intent for Question 2
- Added an utterance such as `Start question 2`
- Added the second question in the opening response
- Reused the existing `CorrectAnswer` and `WrongAnswer` intents
- Built and tested the bot again

---

## Final Outcome
- Successfully built an interactive quiz chatbot using Amazon Lex V2
- Demonstrated intent-based conversation flow and branching logic
- Delivered a stable, user-friendly chatbot without backend code
