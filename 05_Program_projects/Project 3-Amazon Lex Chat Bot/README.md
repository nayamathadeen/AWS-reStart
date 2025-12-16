# AWS Lex Chatbot Project 

## Project Overview

This project focused on designing and building an interactive chatbot using **Amazon Lex** as part of the AWS re/Start programme. The goal was to gain hands-on experience with conversational AI by creating a functional chatbot that could respond to user input and deliver a simple knowledge-check quiz.

The project was divided into two parts:

* **Part 1:** Creating and configuring a basic Amazon Lex bot with intents, utterances, and responses.
* **Part 2:** Extending the bot to deliver an interactive quiz, including handling correct and incorrect user responses.

This project represents my final and most comprehensive practical application of AWS services within the programme.

---

## Services Used

### Amazon Lex

Amazon Lex is an AWS service for building conversational interfaces using voice and text. It uses natural language understanding (NLU) to interpret user input and map it to defined **intents**. Each intent contains **utterances** (what users say) and **responses** (what the bot replies).

In this project, Amazon Lex was used to:

* Create a chatbot (bot) using Lex V2
* Define intents to represent user goals
* Configure opening responses to deliver information and quiz questions
* Simulate branching logic by routing different user inputs to different intents

No backend code or AWS Lambda functions were used, allowing the project to focus purely on Lex fundamentals.

---

## What I Built

### Part 1: Basic Lex Bot

* Created an Amazon Lex bot using English (ZA)
* Added a single intent with sample utterances
* Configured opening responses to provide information about an AWS service
* Built and tested the bot using the Lex test console

This part demonstrated my understanding of the core building blocks of Amazon Lex.

### Part 2: Quiz Chatbot

* Designed a simple knowledge-check quiz using Amazon Lex
* Created a quiz intent that presents a multiple-choice question
* Implemented separate intents to handle correct and incorrect answers
* Used opening responses to provide immediate feedback to the user
* Ensured the bot waits for user input to avoid looping errors

The quiz demonstrated how branching logic can be implemented in Lex without external services.

---

## What I Learned

Through this project, I learned:

* How Amazon Lex V2 differs from older chatbot designs
* How intents and utterances control conversation flow
* How opening responses are used to deliver all bot messages in Lex V2
* How to design conversational flows without causing infinite loops
* How to troubleshoot intent-matching issues and ambiguous user inputs
* How to think about chatbot design from both a technical and user-experience perspective

---

## Skills Developed

This project helped me develop the following skills:

* Conversational AI fundamentals
* Amazon Lex bot configuration
* Intent and utterance design
* Logical flow and branching design
* Debugging and troubleshooting AWS service behaviour
* Explaining technical solutions clearly and confidently

These skills are directly applicable to real-world chatbot, cloud, and customer-interaction solutions.

---

## Challenges Faced

Some of the key challenges I encountered included:

* Understanding where responses are configured in Amazon Lex V2 (opening vs closing responses)
* Designing quiz logic without built-in state management
* Preventing infinite loops caused by intents triggering each other
* Ensuring correct intent matching for similar user inputs
* Adapting project requirements to the actual behaviour of the Lex V2 console

Each challenge required careful testing, refinement of utterances, and a deeper understanding of how Lex processes user input.

---

## Key Takeaway

This project reinforced the importance of simplicity, clarity, and intentional design when working with managed cloud services. Rather than relying on complex logic, I learned how to build reliable and explainable solutions using the native capabilities of Amazon Lex.

The experience has strengthened my confidence in working with AWS services and presenting technical solutions in a structured and professional manner.

---

## Project Status

**Completed**

This project was completed as the final special project for the AWS re/Start programme and is ready for demonstration and portfolio use.
