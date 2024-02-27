# **BASIC CONCEPTS OF MACHINE LEARNING**

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
| **Creation date:** | 25.10.2023              |
| **Version 2.0:**   | 03.01.2024              |
| **Author:**        | Marina Rodrigues Crespo |

# **Inhaltsverzeichnis**

[1 Scope 3](#scope)

[1.1 Document Overview 3](#document-overview)

[1.2 Abbreviations 3](#abbreviations)

[1.3 Revisions 4](#revisions)

[1.4 Referenced Documents 4](#referenced-documents)

[2 AI x Machine Learning x Deep Learning
5](#ai-x-machine-learning-x-deep-learning)

[3 Vector Embedding 6](#vector-embedding)

[3.1 Text Embedding 6](#text-embedding)

[3.2 Documents Embedding 7](#documents-embedding)

[Extra: Calculating Similarity 7](#extra-calculating-similarity)

[3.3 Some interesting use cases 7](#some-interesting-use-cases)

[3.4 Tools to create embeddings 8](#tools-to-create-embeddings)

[4 Choosing a pre-trained language model
8](#choosing-a-pre-trained-language-model)

[Pros and cons of API and Open Source LLMs
8](#pros-and-cons-of-api-and-open-source-llms)

[5 Fine-tuning 9](#fine-tuning)

# 1 Scope

This document aims to provide a foundational understanding of machine
learning, essential for embarking on ML projects. It covers complex
topics, distilled into concise and accessible explanations. Should any
aspect of the content remain unclear or require further clarification,
feedback is welcomed to enhance the document's effectiveness and
comprehensibility.

## Document Overview

This document is structured to provide foundational and advanced
insights into the field of machine learning, with a particular focus on
Large Language Models (LLMs). The key topics covered include:

  - **Artificial Intelligence, Machine Learning, Deep Learning, and
    Large Language Models:** Defines and contextualizes these areas of
    study, establishing a base understanding necessary for future
    AI-projects.

  - **Vector Embedding:** Discusses the technique of transforming
    various types of information into a format suitable for algorithmic
    processing, with a focus on text and document embedding.

  - **Choosing a Pre-trained Language Model:** Guides through the
    considerations in selecting a pre-trained LLM, detailing the
    advantages and disadvantages of using APIs versus open-source
    models, and anticipating further instructional content on local LLM
    implementation.

  - **Fine-tuning:** A overview of the technique and the importance of
    fine-tuning in adapting pre-trained LLMs to specific tasks or
    preferences.

## Abbreviations

This section contains a table of abbreviations utilized throughout this
document, along with their corresponding meanings. They are organized in
alphabetical order for ease of reference.

| AI  | Artificial Inteligence |
| --- | ---------------------- |
| DL  | Deep Learning          |
| LLM | Large Language Model   |
| ML  | Machine Learning       |

## Revisions

| **Revision** | **Actions**                                                             | **Comment**                                                     |
| ------------ | ----------------------------------------------------------------------- | --------------------------------------------------------------- |
| 25.10.2023   | First Issue                                                             |                                                                 |
| 03.01.2024   | The whole document has been rewritten and the DL figure has been added. | The first issue was written spontaneously. It was too informal. |

## Referenced Documents

The documents listed below provide further elaboration and context
related to the contents of this document:

| **Reference and Title**                 | **Document Type**       | **(Rev./Date)** |
| --------------------------------------- | ----------------------- | --------------- |
| Prompt Engineering, RAG and Fine-Tuning | Theoretical Foundations | 02.01.2024      |

# 2 AI x Machine Learning x Deep Learning

**Artificial Intelligence (AI): AI is a broad term encompassing systems
capable of performing tasks autonomously. These tasks range from simple
activities, such as automated vacuuming by robots, to complex operations
often associated with the public's perception of AI.**

**Machine Learning (ML): Machine Learning is a subset of AI that enables
systems to learn and improve from experience without being explicitly
programmed. It encompasses various methods, each allowing systems to
undertake increasingly complex tasks beyond the capabilities of early AI
techniques that required explicit programming for every function.**

**Deep Learning (DL): Deep Learning, a specialized method of Machine
Learning, employs neural networks with multiple layers, including input,
output, and hidden layers (see** Figure 1**). The computations in these
hidden layers, while intricate and not fully transparent (often referred
to as the "black box" problem), enable the solving of complex tasks.
This area is a focus of ongoing research aimed at understanding and
improving interpretability.**

![Ein Bild, das Entwurf, Diagramm, Zeichnung, Reihe enthält. Automatisch
generierte Beschreibung](media/image3.png)

Figure 1: Graphical representation of a deep neural network. The
computations that take place in the hidden layers to predict outputs
cannot be understood by humans.

**Large Language Models (LLMs): In contemporary discussions about AI,
deep learning, particularly through neural networks, is often at the
forefront. LLMs, such as ChatGPT, are prominent examples that utilize
deep learning for natural language processing. While these models can
interpret and generate text, it's essential to note that they don't
"understand" language as humans do. Instead, they translate text into
numerical representations called "vector embeddings," allowing the
machine to process language data.**

# 3 Vector Embedding

Vector embedding is a technique employed to represent various types of
information — including text, images, video, and audio — in a format
conducive to processing by algorithms, particularly those in DL.
Converting this information into a numerical format is essential for
processes such as training, Retrieval-Augmented Generation (RAG), and
fine-tuning.

## 3.1 Text Embedding

In text embedding, words are transformed into numerical arrays, enabling
computers to interpret and process their meanings. This numerical
representation allows the model to understand the semantic proximity
between words. For example, the numerical representation of "bank" is
closer to "chair" than to "elephant," indicating a semantic similarity.
A well-known illustration of text embedding is the equation:

king – man + woman = queen

In this equation, while various results are possible (e.g., "throne,"
"prince," "daughter," "elizabeth"), the most probable outcome provided
by the model is "queen." This example demonstrates how models use
numerical representations to predict and understand the relationship
between words.

***Extra (for the curious): This is the meaning of the word "Canada" for
a model.***

![Ein Bild, das Text, Screenshot, Schrift, Zahl enthält. Automatisch
generierte Beschreibung](media/image4.png)

## 3.2 Documents Embedding

Similar to words, entire documents can be embedded to facilitate the
calculation of semantic similarity. This capability is instrumental in
using LLMs for organizing documents based on similarity, enabling
applications like document classification and semantic search..

### Extra: Calculating Similarity

Models often employ "cosine similarity" to quantify the degree of
similarity between documents. Cosine similarity values range from -1 to
1, with values closer to -1 or 1 indicating higher similarity and values
near 0 indicating lower similarity. This measure helps to determine how
closely the meanings of two documents align.

## 3.3 Some interesting use cases

  - **Anomaly Detection:** By converting data into vectors, models can
    identify outliers or anomalies by measuring deviations in
    similarity. This is useful in detecting missing information or
    potential errors in documents.

  - **Transfer Learning:** Leveraging pre-trained embeddings allows for
    effective transfer of knowledge to new tasks, particularly when
    there is limited data available for the target task.

  - **Information Retrieval:** Embedding both queries and documents in a
    shared space enables the retrieval of documents that semantically
    correlate with the query, beyond mere keyword matching. This is also
    foundational in various Natural Language Processing (NLP) tasks,
    familiar through technologies like ChatGPT.

## 3.4 Tools to create embeddings

A variety of tools and frameworks exist to facilitate the creation of
embeddings, such as OpenAI's suite of technologies, Word2vec, and GloVe
among others. A critical consideration in selecting an embedding tool is
compatibility with the foundation model's original embedding. Ensuring
the same embedding tool is used throughout is essential for maintaining
consistency and effectiveness in the embedding process.

# 4 Choosing a pre-trained language model

Building a language model requires an extensive dataset, a
resource-intensive endeavor typically feasible for only a few
organizations, such as OpenAI. For our projects, we generally have two
options: utilizing an API of a LLM or employing an open-source LLM.

### Pros and cons of API and Open Source LLMs

**APIs**

  - Example: OpenAI's GPT models.

  - Pros: Higher performance due to more extensive training data.

  - Cons: Usage involves transmitting information to OpenAI.

  - Conclusion: Suitable if the data used for fine-tuning is not
    confidential.

**Open Source LLMs**

  - Example: The Hugging Face library, which hosts a variety of
    open-source models, including their own model, Bloom, developed
    collaboratively by thousands of researchers and developers.

  - Pros: Can be run locally, offering enhanced data security.

  - Cons: Generally less effective than OpenAI's API models due to
    smaller training datasets.

  - Conclusion: Preferable when privacy is paramount. Performance can be
    improved using techniques such fine-tuning and RAG\[1\].

Implementing a local Large Language Model (LLM) involves several
complexities, including considerations of the model's size, language,
and task suitability. To assist future project collaborators, I intend
to compile a comprehensive guide on utilizing local LLMs. As machine
learning projects become increasingly common, this guide will serve as a
valuable resource, providing detailed advice on selecting and employing
the right model for specific tasks.

**In Summary:** A detailed “How-to” guide for using open-source LLMs
locally will be developed.

# 5 Fine-tuning

Fine-tuning is the process of customizing a pre-trained LLM for specific
tasks or styles. This is achieved by further training the model on a
targeted dataset. A key aspect of fine-tuning is instruction tuning,
which involves training the model using a series of task-specific
instructions in natural language. For an in-depth exploration of
fine-tuning techniques and strategies for optimizing results, refer to
the document “Prompt Engineering, RAG and Fine-tuning.”

1.  More about fine-tuning and RAG in the document “Prompt Engineering,
    RAG and Fine-Tuning”
