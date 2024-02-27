# **Wiki.JS  
  
Used for RAG**

|                    |                   |
| ------------------ | ----------------- |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
| **Creation date:** | 24.01.2024        |
| **Version 1.0:**   | 24.01.2024        |
| **Author:**        | Chiragkumar Patel |

# **Table of contents**

[Table of contents 1](#table-of-contents)

[1. Using Wiki.JS as a Source for RAG
2](#using-wiki.js-as-a-source-for-rag)

[2. Installation and setup of Wiki.JS
3](#installation-and-setup-of-wiki.js)

[3. Integration with Retrieval Model
3](#integration-with-retrieval-model)

[3.1 What are Retrieval Models? 3](#what-are-retrieval-models)

[3.2 Integration with Solr 3](#integration-with-solr)

[3.3 Integration with Elasticsearch 6](#integration-with-elasticsearch)

**Table of figures**

No table of figures entries found.

## Using Wiki.JS as a Source for RAG

We can use different sources for RAG as per the application needs and
complexity but for our case we will be using Wiki.JS as source database
for all the retrieval processes. Using Wiki.JS as a Retrieval-Augmented
Generation (RAG) system involves setting up the Wiki.JS platform for
storing relevant documents and then integrating it with a natural
language processing (NLP) model capable of generating text based on
retrieved information. In order to Integrate Wiki.JS with RAG, we need
to follow some steps as mentioned,

  - Setup document database in Wiki.JS

  - Integration with Retrieval Model

  - Configuration of Generation Model

Let’s understand it step by step.

## Installation and setup of Wiki.JS

Install Wiki.JS on a private server using Node.js and MongoDB. Populate
Wiki.JS with documents relevant to the domain, ensuring proper
categorization and tagging.

## Integration with Retrieval Model

There are multiple retrieval models available which can be chosen by the
need to application. You can use Elasticsearch or Solr for local
deployment. Install and configure the chosen search engine on your
private server to index and search through the documents stored in
Wiki.JS.

Ensure that the retrieval model is accessible within your private
network. Configure net-work settings and security protocols accordingly.
Implement a local API or interface for querying the retrieval model from
your chatbot application.

### What are Retrieval Models?

Based on a user's query, a retrieval model selects and ranks relevant
pages. Since documents and queries are structured in the same way,
document selection and ranking may be formalized using matching
functions that return retrieval status values for each document in a
collection. Most information retrieval systems use a set of words from a
vocabulary as a collection of descriptors to represent the contents of
documents. In short, Information Retrieval is about quickly finding
materials in a large collection of unstructured data.

### Integration with Solr

Solr is a search server built on top of Apache Lucene, an open source,
Java-based, information retrieval library. Solr is designed to drive
powerful document retrieval or analytical applications involving
unstructured data, semi-structured data or a mix of unstructured and
structured data.

Solr’s query syntax and parsers offer support for everything from the
simplest keyword searching through to complex queries on multiple fields
and faceted search results. Queries are transmitted to Solr via HTTP 1.1
or 2.0 requests and the response is typically a list of structured
document descriptors. In the classic example, 10 descriptors are
returned, each including a URL (example from an [YouTube
video](https://www.youtube.com/watch?v=2VkFQTqrRYo) shown in an Image
below) to locate the document (often rendered as "10 blue links"). JSON
is the default response format, but it could also be XML, CSV, optimized
binary, or (with customization) any format you desire.

The detailed documentation can be found on the web-page of Solr,

<https://solr.apache.org/guide/solr/latest/getting-started/introduction.html>

![Image](media/image4.png)

Figure 1: Example of retrieved documents containing text "brad pitt"

**<span class="underline">Advantages of Solr:</span>**

  - Robust and Mature: Solr is a mature and stable search platform with
    a long history of development and use in production environments.

  - Flexible Configuration: Solr offers flexible configuration options
    and supports a wide range of indexing and search features, including
    faceted search, spatial search, and highlighting.

  - Scalability: Similar to Elasticsearch, Solr supports horizontal
    scalability, allowing you to scale your search infrastructure as
    needed.

  - Community Support: Solr has a large and active community of users
    and developers, providing access to extensive documentation,
    tutorials, and support resources.

  - Integration: Solr integrates well with other Apache projects and
    ecosystem tools, such as Apache Hadoop, Apache Spark, and Apache
    Nutch.

**<span class="underline">Dis-advantages of Solr:</span>**

  - Complexity: Like Elasticsearch, Solr can be complex to set up and
    configure, especially for large-scale deployments with advanced
    features.

  - Resource Requirements: Solr requires significant resources,
    including memory, disk space, and CPU, particularly for indexing and
    handling large datasets.

  - Configuration Overhead: Configuring Solr involves dealing with XML
    configuration files, which may be daunting for users unfamiliar with
    XML syntax.

Here is a quick guide on How to do the integration of Retrieval Model
with Solr:

**Step 1:** Install Solr

  - Download and Install Solr on your server or a separate machine.

  - Follow the Installation guidelines provided in the Solr
    documentation.

  - Configure Solr to run as s service and adjust settings such as
    memory allocation and network configuration as needed.

**Step 2:** Configure Core

  - Create a core in Solr to store Wiki.JS documents.

  - Define a schema.xml file that specifies how each document field
    should be indexed and analyzed.

  - Use the Solr Admin UI or command-line tools to upload Wiki.JS
    documents to the core.

**Step 3:** Synchronize it with Wiki.JS

  - Implement a synchronization mechanism to keep Solr core updated with
    changes in Wiki.JS.

  - This can be done using plugins like DatalmportHandler or by
    developing a custom connector that monitors changes in Wiki.JS and
    updates Solr accordingly.

**Step 4:** Querying Solr

  - Develop a query mechanism in your chatbot application to send user
    queries to Solr.

  - Use Solr’s Query syntax to construct queries that match user intent
    and retrieve relevant documents.

  - Handle Solr responses to extract relevant document IDs or content
    for further processing.

### Integration with Elasticsearch

Elasticsearch is a distributed, open-source search and analytics engine
built on Apache Lucene and developed on Java. Fundamentally,
Elasticsearch organizes data into documents, which are JSON-based units
of information representing entities.

Documents are grouped into indices, similar to databases, based on their
characteristics. Elasticsearch uses inverted indices, a data structure
that maps words to their document locations, for an efficient search.
Elasticsearch’s distributed architecture enables the rapid search and
analysis of massive amounts of data with almost real-time performance.

At its core, you can think of Elasticsearch as a server that can process
JSON requests and give you back JSON data.

The link for the official documentation on Elasticsearch:
<https://www.elastic.co/guide/en/elasticsearch/reference/8.12/elasticsearch-intro.html>

**<span class="underline">Advantages of Elasticsearch:</span>**

  - Scalability: Elasticsearch is highly scalable, allowing you to
    easily scale by adding more nodes to your information cluster.

  - Full-Text Search: Elasticsearch provides powerful full-text search
    capabilities, including support for stemming, synonyms, and
    relevance scoring.

  - Real-Time Data: Elasticsearch supports real-time indexing and
    search, making it suitable for applications that require up-to-date
    information.

  - Rich Query DSL: Elasticsearch offers a rich Query DSL (Domain
    Specific Language) for constructing complex queries, enabling
    fine-grained control over search behavior.

  - Ecosystem: Elasticsearch has a large and active ecosystem with
    extensive documentation, community support, and third-party plugins
    for various use cases.

> **<span class="underline">Dis-advantages of Elasticsearch:</span>**

  - Complexity: Setting up and configuring Elasticsearch can be complex,
    especially for beginners or smaller deployments.

  - Resource Intensive: Elasticsearch can be resource-intensive,
    requiring sufficient memory, disk space, and CPU resources to
    operate efficiently.

  - Learning Curve: Learning to use Elasticsearch effectively requires
    familiarity with its concepts, APIs, and query language, which may
    have a steep learning curve for some users.

Here is a quick guide on How to do the integration of Retrieval Model
with Elasticsearch:

**Step 1:** Install Elasticsearch

  - Download and Install Elasticsearch on your server or a separate
    machine.

  - Follow the Installation guidelines provided in the Elasticsearch
    documentation.

  - Configure Elasticsearch to run as s service and adjust settings such
    as memory allocation and network configuration as needed.

**Step 2:** Set-up Indexing

  - Create an index in Elasticsearch to store the Wiki.JS documents.

  - Define a mapping list that specifies how each document field should
    be indexed and analyzed.

  - Use the Elasticsearch Index API or bulk indexing to add Wiki.JS
    documents to the index.

**Step 3:** Synchronize it with Wiki.JS

  - Implement a synchronization mechanism to keep Elasticsearch index
    updated with changes in Wiki.JS.

  - This can be done using plugins like Elasticsearch River or by
    developing a custom connector that monitors changes in Wiki.JS and
    updates Elasticsearch accordingly.

**Step 4:** Querying Elasticsearch

  - Develop a query mechanism in your chatbot application to send user
    queries to Elasticsearch.

  - Use Elasticsearch Query DSL to construct queries that match user
    intent and retrieve relevant documents.

  - Handle Elasticsearch responses to extract relevant document IDs or
    content for further processing.
