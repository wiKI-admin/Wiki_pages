# **Prompt Engineering, RAG and Fine-tuning**

# **  
THEORETICAL FOUNDATIONS**

|                    |                         |
| ------------------ | ----------------------- |
|                    |                         |
|                    |                         |
|                    |                         |
|                    |                         |
|                    |                         |
|                    |                         |
|                    |                         |
|                    |                         |
|                    |                         |
|                    |                         |
|                    |                         |
|                    |                         |
| **Creation date:** | 02.01.2024              |
| **Version 1.0:**   | 02.01.2024              |
| **Author:**        | Marina Rodrigues Crespo |

# **Inhaltsverzeichnis**

[1 Scope 3](#scope)

[1.1 Document Overview 3](#document-overview)

[1.2 Abbreviations 3](#abbreviations)

[1.3 Revisions 4](#revisions)

[1.4 Referenced Documents 4](#referenced-documents)

[2 Prompt Engineering 4](#prompt-engineering)

[3 Prompt engineering + Retrieval-Augmented Generation (RAG)
5](#prompt-engineering-retrieval-augmented-generation-rag)

[3.1 Why RAG? 6](#why-rag)

[3.2 RAG Overview 6](#rag-overview)

[Preparation 6](#preparation)

[Retrieval (simplified) 7](#retrieval-simplified)

[Retrieval (advanced) 7](#retrieval-advanced)

[4 Fine-tuning 8](#fine-tuning)

[Cases where fine-tuning is useful
8](#cases-where-fine-tuning-is-useful)

[Fine-tuning misconceptions: 8](#fine-tuning-misconceptions)

[4.1 Fine-tuning Strategies 9](#fine-tuning-strategies)

[4.2 Fine-tuning for tasks: An Extension to Few-shot Learning
9](#fine-tuning-for-tasks-an-extension-to-few-shot-learning)

[5 Retrieval + Tuning 11](#retrieval-tuning)

[6 Sources/Literature 11](#sourcesliterature)

# Scope

This document aims to detail the methodologies and applications of
Prompt Engineering, Retrieval-Augmented Generation (RAG), and
fine-tuning in Large Language Models (LLMs). It discusses how these
techniques improve LLM functionality, accuracy, and efficiency in
language processing and generation tasks. The document focuses on the
theory with some implementation examples. In the future, this document
should be reviewed to include more practical examples from Akkodis
projects.

## Document Overview

This document includes:

  - **Prompt Engineering (page** **4):** Discusses the use of prompts to
    guide and customize the behavior of LLMs.

  - **Retrieval-Augmented Generation (RAG, page** **6):** Examines the
    integration of external knowledge into LLM responses through RAG.
    This section outlines the mechanism, applications, and strategies
    for effectively using RAG.

  - **Fine-tuning (page** **8):** Explains the process of fine-tuning
    LLMs for specific tasks or styles. It covers the applications,
    benefits, common misconceptions, and strategies of fine-tuning,
    including an introduction to few-shot learning.

## Abbreviations

This section contains a table of abbreviations utilized throughout this
document, along with their corresponding meanings. They are organized in
alphabetical order for ease of reference.

| LLM | Large Language Model           |
| --- | ------------------------------ |
| RAG | Retrieval Augmented Generation |

## Revisions

| **Rev** | **Actions** | **Comment** |
| ------- | ----------- | ----------- |
| \-      | First Issue |             |

## Referenced Documents

The documents listed below provide further elaboration and context
related to the contents of this document:

| **Reference and Title**    | **Document Type**       | **(Rev./Date)** |
| -------------------------- | ----------------------- | --------------- |
| Basics of Machine Learning | Theoretical foundations | ADD             |

# Prompt Engineering

Prompts are instructions given to Large Language Models (LLMs)\[1\] to
enforce rules, automate processes, and ensure specific qualities (and
quantities) of generated output. As a form of programming, prompt
engineering customizes the outputs and interactions with an LLM, making
it a critical skill for developers and researchers working with these
models.

For instance, a prompt might be designed to ensure that an LLM generates
code following a certain coding style or programming paradigm. It might
also instruct the LLM to flag certain keywords or phrases in a generated
document and provide additional, relevant information related to those
keywords.

**Prompt engineering** is essentially programming via prompts. To
illustrate it, consider this prompt:

> “From now on, I would like you to ask me questions to deploy a Python
> application to AWS. When you have enough information, create a Python
> script to automate the deployment.”

This prompt instructs the model to initiate an interactive session,
asking the user questions about their software application. It will
continue this question-asking process until it has gathered enough
information to generate a Python script automating the AWS deployment.
This example demonstrates the programming potential of prompts beyond
conventional “generate a method that does X” style prompts or “answer
this quiz question”.

Here are some components that can be part of a prompt:

  - **Priming :** „You are a plumbing Q\&A bot that answers questions
    about plumbing in a helpful way”

  - **Style and tone instructions :** “Use 10<sup>th</sup> grade
    language and explain things in a simple way that anyone can
    understand.” (based on the audience)

  - **Handling errors & edge cases :** “If a question is irrelevant to
    plumbing, gently decline to offer because it’s not your area of
    expertise.”

  - **Dynamic content :** User inquiry like “How do I fix a leaky
    faucet?”

  - **Output formatting :** Respond in a valid JSON object to be
    consumed by a application, following this pattern : {“response”,
    “your response goes here”}

While prompt engineering can greatly enhance the functionality and user
experience of LLMs, it is important to be aware of its limitations.
Misunderstandings or overly complex instructions can lead to unintended
outputs. Consequently, prompt engineering is an iterative and careful
process, requiring continuous refinement and understanding of the
model's capabilities and limitations.

# Prompt engineering + Retrieval-Augmented Generation (RAG)

Retrieval-Augmented Generation (RAG) is a technique that augments the
responses of LLMs by retrieving relevant information from external
knowledge bases before generating answers. This additional content
dynamically supplements the prompt, providing a richer, more accurate,
and up-to-date response.

**Example of Prompt Engineering with RAG (underlined):**

> “You are a plumbing Q\&A bot that answers questions about plumbing in
> a helpful way.
> 
> Use 10<sup>th</sup> grade language and explain things in a simple way
> that anyone can understand.
> 
> If a question is irrelevant to plumbing, gently decline to offer
> because it’s not your area of expertise.
> 
> User inquiry: {inquiry}
> 
> **<span class="underline">Use this to help if relevant:
> {knowledge}</span>**
> 
> Respond in a valid JSON object to be consumed by an application,
> following this pattern: {“response”, “your response goes here”}”
> 
> Inquiry = “How do I fix a leaky faucet?”
> 
> Knowledge = “Plumbers Handbook, Chapter 1: Fixing Common leaks”

## Why RAG?

Models are trained on vast corpora but don't retain quotes verbatim;
they predict the most likely tokens, returning summaries or paraphrases
as the information is compressed into these probabilities. To guide a
model to use specific, accurate information, we need to provide it
directly in the prompt. LLMs excel at processing and adhering to the
information given in prompts, allowing for the expansion of knowledge
and the integration of real-time data from external sources.

## RAG Overview

### Preparation 

  - **Corpus:** Assemble a database containing the necessary information
    (e.g., web pages, PDFs, books, Wikipedia, etc.).

  - **Split:** Divide texts into chunks in a way that maintains context
    and coherence (e.g., by paragraph, by section).

  - **Embed:** Convert the text into embeddings, vector representations
    that facilitate similarity comparisons.

  - **Store:** Save the text and its embeddings in the vector database.

### Retrieval (simplified)

  - **Inquiry:** "How do I fix a leaky faucet?"

  - **Embed:** Use the same model as stored embeddings to vectorize the
    inquiry.

  - **Search:** Retrieve the 3-5 most relevant results from the vector
    database.

  - **Build Prompt:** Incorporate the results into the prompt sent to
    the response generator.

Retrieval may seem simple here, but to get consistent results for all
types of inquiries there are many optimization steps that need to be
added. They will be shown in the next section.

### Retrieval (advanced) 

  - **Inquiry:** "How do I fix a leaky faucet?"

  - **Pre-process:** Convert the inquiry into a more specific keyphrase
    that aligns with the database chunks.

  - **Filter:** Use the LLM to determine the most applicable result
    before including it in the prompt.

  - **Build Prompt:** Construct the prompt with the filtered result for
    response generation.

  - **Self-Reflect: Before finalizing the response, the LLM reviews its
    own answer for accuracy and coherence.** Example: "Is this a good
    and accurate answer? If not, rewrite it." This gives the LLM another
    opportunity to correct possible errors in the answer

# Fine-tuning

Fine-tuning involves further training a foundation model on a specific
dataset to refine its predictions for specific tasks. It's about
teaching the model the nuances of language, style, or domain-specific
knowledge that general training may not cover. By providing the model
with examples of prompts and their ideal completions, fine-tuning
adjusts the model's underlying weights, enhancing its performance on
specialized tasks.

### Cases where fine-tuning is useful 

1.  **Teaching intuition:** Helping the model understand subtle nuances
    in text or context.

2.  **Baking in Style, Tone, and Formatting:** Ensuring consistent
    style, tone, and formatting in outputs.

3.  **Reducing Prompt Length:** Enabling longer completions within the
    context window with shorter prompts.

4.  **Training Smaller Models for Specialized Tasks:** Building smaller,
    more efficient models that perform well on specific tasks,
    addressing sustainability concerns as continuously making models
    larger isn't viable due to increased computational requirements.

5.  **Narrowing the Range of Possible Outputs:** Focusing the model's
    responses to be more predictable and aligned with desired outcomes.

### Fine-tuning misconceptions

  - **It teaches the model "facts":** Models don't store facts but
    rather predict probabilities. For factual responses, RAG with
    context augmentation is more appropriate.

  - **It requires a large dataset:** This is no longer true, modern
    foundation models can achieve significant improvements with
    relatively small datasets, such as 20.

  - **It’s too expensive:** This is no longer true either, as today we
    have parameter efficient fine-tuning techniques.

## Fine-tuning Strategies 

**Strategy \#1: Quality First**

**Train larger models with high-quality output examples. This is akin to
an advanced form of few-shot learning. Because the models are larger,
they require smaller training dataset.**

**Strategy \#2: Speed & Cost Optimization**

**Train smaller models to perform specific tasks efficiently,
potentially requiring a larger dataset.**

**Important: the larger the model, the less data you need and vice
versa.**

## Fine-tuning for tasks: An extension to few-shot learning

**Few-shot learning involves providing the model with a few examples to
guide its understanding of a specific task. For instance, when training
a model to classify sales leads, you might provide examples of qualified
and unqualified inquiries:**

> **“You are a sales lead qualifier that will determine where a website
> form submission for a plumbing company is qualified or unqualified.**
> 
> **Examples:**
> 
> **Help\! I just had a pipe break in my house and there’s water
> everywhere. Send someone ASAP.**

  - Qualified

> **We are offering a special small business package to new Dunder
> Mifflin customers.**

  - Unqualified

> **Now qualify this form submission:**
> 
> **{form\_submission}”**

**With fine-tuning, these examples can be incorporated into the dataset.
With as few as around 20 examples, you might begin to observe changes in
the model's behavior. This is crucial for training a model for specific
tasks that will be executed repeatedly. The task previously mentioned as
an example can be formatted as follows for a model that has been
fine-tuned for this specific task:**

> **“You are a sales lead qualifier that will determine where a website
> form submission for a plumbing company is qualified or unqualified.**
> 
> **Now qualify this form submission:**
> 
> **{form\_submission}”**

The training data for this task could be the following one:

| **Help\! I just had a pipe break in my house and there’s water everywhere. Send someone ASAP.**                  | Qualified   |
| ---------------------------------------------------------------------------------------------------------------- | ----------- |
| **We are offering a special small business package to new Dunder Mifflin customers.**                            | Unqualified |
| Are you able to provide a quote on replacing 3 toilets with new water efficient ones?                            | Qualified   |
| Can u give me a call and I need advice on some personal matters. I think my cat is planning something nefarious. | Unqualified |

# Retrieval + Tuning 

To optimize performance, it is advantageous to combine RAG with
fine-tuning, applying both to the same template for superior outcomes.
When a model that has been fine-tuned incorporates RAG, the prompts
primarily consist of dynamic content that adapts to the specific inquiry
or context, like in the following example:

> {Inquiry}
> 
> {knowledge}

# Sources/Literature 

  - [Prompt Engineering, RAG, and Fine-tuning: Benefits and When to Use
    (youtube.com)](https://www.youtube.com/watch?v=YVWxbHJakgg)

  - [\[2303.18223\] A Survey of Large Language Models
    (arxiv.org)](https://arxiv.org/abs/2303.18223)

  - Retrieval-Augmented Generation for Large Language Models: A Survey
    [2312.10997.pdf (arxiv.org)](https://arxiv.org/pdf/2312.10997.pdf)

  - [\[2302.11382\] A Prompt Pattern Catalog to Enhance Prompt
    Engineering with ChatGPT
    (arxiv.org)](https://arxiv.org/abs/2302.11382)

<!-- end list -->

1.  More information about LLMs can be found in the document "Basics of
    Machine Learning."
