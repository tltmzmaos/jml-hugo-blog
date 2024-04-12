---
title: 👩🏼‍🏫 PDF ChatBot
summary: Large Language Model, OpenAI, Embedding, Vector DB
date: 2024-04-11
math: true
authors:
  - admin
tags:
  - ChatBot
  - LLM
  - OpenAI
  - Embedding
  - Vector DB
image:
  caption: "Hello My ChatGPT"
---

# What is Large Language Model(LLM)?

A large language model (LLM) is a language model notable for its ability to achieve general-purpose language generation and other natural language processing tasks such as classification. LLMs acquire these abilities by learning statistical relationships from text documents during a computationally intensive self-supervised and semi-supervised training process. LLMs can be used for text generation, a form of generative AI, by taking an input text and repeatedly predicting the next token or word.

# Concern 1 - What model should I use?

Through ChatGPT, I began to take an interest in Generative AI, and I've already learned that many excellent models, including those on [HuggingFace](https://huggingface.co/), are available for free or under licenses through various avenues. I've decided to utilize models that are frequently used or mentioned in the Q&A format, which are suitable for my project.

The lists of LLM models were further divided based on the number of parameters available for each model, and I decided to compare the models below.

- [ChatGPT](###ChatGPT)
- [Titan](###Titan)
- [Mistral](###Mistral)
- [Llama 2](###Llama2)

## Comparisons

Based on the analytic comparisons from [Artificial Analysis AI](https://artificialanalysis.ai/models), GPT4 showed the best performance, but pricing was an issue. As for Llama 2, while its 70B model could be compared to the previously mentioned models, it's too large to host directly, and it seems that no API is provided. It seems that GPT3.5 and Mistral models are proper to use for my project.
![](content/POC/PDF%20Chatbot/comparison.png)

## LLM list

### ChatGPT

No need to explain about ChatGPT. Too many people are already using it and it has been verified for its performance and quality by the public. ChatGPT was created by OpenAI and is a form of generative AI that uses a Generative Pre-trained Transformer (GPT) to process requests and formulate responses. It is trained with reinforcement learning through human feedback and reward models that rank the best responses.

### Titan

Titan is created by Amazon and it is exclusively available on AWS Bedrock. The model provides a fully managed API that offers a variety of high-performance image, multi-model, and text models to customers. The models are built and pre-trained on large datasets in AWS, making them powerful and versatile models that support responsible AI use across various use cases.

### Mistral

Mistral is a large language model developed by Mistral AI, a French AI company. It is designed to understand and generate human-like text in a variety of languages, including English, French, German, Spanish, and many others. Mistral is a powerful language model that is well-suited for a wide range of natural language processing tasks. Its multilingual capabilities make it a valuable tool for businesses and organizations that operate in multiple languages, and its powerful language generation capabilities make it well-suited for conversational AI and content generation applications.

### Llama2

A large language model developed by Meta, the parent company of Facebook. It is an open source model that is available for research and commercial purposes, making it a significant development in the AI space. Llama 2 is designed to predict the most plausible follow-on text using its neural network, which is modeled after the human brain. It is trained with 2 trillion tokens from publicly available sources like Common Crawl, Wikipedia, and public domain books from Project Gutenberg.

# Concern 2 - Where do I use?

Ultimately, I had no choice but to either deploy the models myself or utilize provided APIs, as I wanted these projects to be accessible not only on my laptop but also regardless of the equipment and location. For me, the most important aspect was achieving performance that exceeded a certain threshold relative to the minimum cost.

More research is needed on hosting the model directly, but methods such as deploying it on Cloud (e.g., AWS EC2, SageMaker) or using HuggingFace seemed expensive based on the usage I had in mind, so I excluded them from the comparison group.

The price comparison below only includes places where solutions are provided, and there may be a wider range of services available beyond the content below.

## Price Comparison

> Price is based on 04/07/2024

| Service                                               | Model Name             | Input Price (1,000 tokens) | Output Price (1,000 tokens) |
| ----------------------------------------------------- | ---------------------- | -------------------------- | --------------------------- |
| [OpenAI](https://openai.com/pricing)                  | gpt-3.5-turbo-0125     | $0.0005                    | $0.0015                     |
|                                                       | gpt-3.5-turbo-instruct | $0.0015                    | $0.0020                     |
|                                                       | gpt-3.5-turbo-1106     | $0.0010                    | $0.0020                     |
| [AWS Bedrock](https://aws.amazon.com/bedrock/pricing) | Titan Text Lite        | $0.0003                    | $0.0004                     |
|                                                       | Titan Text Express     | $0.0008                    | $0.0016                     |
|                                                       | Mixtral 8\*7B          | $0.00045                   | $0.0007                     |
|                                                       | Mixtral 7B             | $0.00015                   | $0.0002                     |
| [DeepInfra](https://deepinfra.com/models)             | Mixtral 8\*7B Chat     | $0.00027                   | $0.00027                    |
|                                                       | OpenChat-3.5           | $0.00013                   | $0.00013                    |
|                                                       | Mistral-7B             | $0.00013                   | $0.00013                    |

The usage I had in mind was estimating a maximum of 1000 input tokens and 2000 output tokens per day. It depends on what question I ask, but this is higher than the actual amount I use in the ChatGPT website.

The price would be as follows per a month:

|                                                       | Model                  | Price ($/day) | Price ($/month) |
| ----------------------------------------------------- | ---------------------- | ------------- | --------------- |
| [OpenAI](https://openai.com/pricing)                  | gpt-3.5-turbo-0125     | $0.0035       | $0.105          |
|                                                       | gpt-3.5-turbo-instruct | $0.0055       | $0.165          |
|                                                       | gpt-3.5-turbo-1106     | $0.005        | $0.15           |
| [AWS Bedrock](https://aws.amazon.com/bedrock/pricing) | Titan Text Lite        | $0.0011       | $0.033          |
|                                                       | Titan Text Express     | $0.004        | $0.12           |
|                                                       | Mixtral 8\*7B          | $0.00185      | $0.0555         |
|                                                       | Mixtral 7B             | $0.00055      | $0.0165         |
| [DeepInfra](https://deepinfra.com/models)             | Mixtral 8\*7B Chat     | $0.00081      | $0.0243         |
|                                                       | OpenChat-3.5           | $0.00039      | $0.0117         |
|                                                       | Mistral-7B             | $0.00039      | $0.0117         |

Honestly, the price is less than I though and I think that I can go with any models I want to use. Then, I also think that let's give OpenAI a try due to the large community.

# Conclusion

After comparing price and performance, it seems that a cost within the acceptable range per month can be achieved. The gpt-3.5-turbo-0125 model, which has many usage examples, appears to be the most suitable model currently. Of course, as the project develops further, various attempts will be made, but the plan is to decide on the model to use and move on to the next steps afterward.

# Reference

- Wikipedia: [https://en.wikipedia.org/wiki/Large_language_model](https://en.wikipedia.org/wiki/Large_language_model)
- OpenAI: [https://openai.com/](https://openai.com/)
- Mistral AI: [https://mistral.ai/](https://mistral.ai/)
- Llama 2: [https://llama.meta.com/llama2/](https://llama.meta.com/llama2/)
- AWS Bedrock: [https://aws.amazon.com/](https://aws.amazon.com/)
- Artificial Analysis AI: [https://artificialanalysis.ai/models](https://artificialanalysis.ai/models)
