# Lilys-Bloom-Bot

# Serverless Retrieval-Augmented Conversational AI using Amazon Bedrock, Lex, and Vector Search

BloomBot is a conversational assistant for Lily's Bloom Boutique Flower Shop that provides product recommendations, delivery information, and policy support using retrieval-augmented generation powered by Amazon Bedrock.

System Architecture

<img width="785" height="351" alt="Screenshot 2026-03-02 at 5 44 15 PM" src="https://github.com/user-attachments/assets/fb32cfa0-6893-43bf-af81-793646dbaebf" />

Demo

https://github.com/user-attachments/assets/3bbe1805-8798-4ff1-afcc-185ae8102f13

# Implementation Process

# Knowledge Base

Structured retail documents were created to simulate a real flower shop environment:

Product catalog (bouquets, prices, SKUs)
Delivery policies
Return & freshness policy
Care instructions
Substitution rules
Store information
FAQ
Occasion-based recommendations

These documents serve as the source of truth for the assistant. All of them went in an S3 bucket.

The Knowledge Base was configured with:
Max chunk size: 500 tokens
Overlap: 20%
Used Claude Haiku as the model. 

When a user submits a query:
The query is converted into an embedding.
The vector store retrieves semantically similar document chunks.
Retrieved context is injected into the prompt.
Claude 3.5 Haiku generates a grounded response.
This process reduces hallucinations and ensures answers are based on the shop’s actual documentation.

# Conversational Orchestration (Amazon Lex)

Amazon Lex handles:
Intent classification
Fallback handling for gibberish or unsupported queries
Routing user messages to Lambda

Lex enables structured conversation management while Bedrock handles knowledge-based reasoning.

# My experience

This was a very fun and information project to work with. I decided to go with this project as it is something that real enterprises may use.
In the age of AI, business or internal team chat bots are on the rise and it is important to understand how they are made and implemented.

To build on this project, I want to create an API and my own UI that interacts with the knowledge base instead of using Lex.

Thank you 🌸 
