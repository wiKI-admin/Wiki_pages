**What is YAML?**

YAML is a Human readable data serialization language which can be used
for writing configuration files in all programming languages. YAML is a
short form of “YAML Ain’t Markup Language or “Yet Another Markup
Language”. It is generally used for data exchange, configuration files,
and storing metadata. But it can also be used to represent arbitrary
date structures such as lists, arrays, and dictionaries.

**Features of YAML**

YAML includes a markup language with important construct, to distinguish
data-oriented language with the document markup. The design goal and
features of YAML are,

  - It matches native data structures of agile methodology and its
    languages such as Python, PHP, Ruby, and JavaScript.

  - It is portable between programming languages

  - It includes data consistent data model.

  - Easily readable by humans

  - Ease of Implementation and usage

**Basic YAML Syntax**

A YAML syntax primarily uses 3 node types:

1.  <span class="underline">Mapping:</span> The content of a mapping
    node is an unordered set of key/value node pairs, with the
    restriction that each of the keys is unique.

2.  <span class="underline">Sequences:</span> The content of the
    sequence node is an ordered series of zeros or more nodes. A
    sequence can contain the same node more than once. It can even
    contain itself.

3.  <span class="underline">Scalar:</span> The content of the scalar
    node is an opaque data that can be represented as a series of zero
    or more Unicode characters.

**Synopsis of YAML Basic Elements**

  - Comments begin with (**\#**) Character.

  - Comments must be separated from other tokens by whitespaces.

  - Tabs are not included as Indentation (the space at the beginning of
    a line of writing) for YAML files.

  - List members are denoted by a leading hyphen (**-**).

  - List members are enclosed in square brackets and separated by
    commas.

  - Associative arrays are represented using colon **( : )** in the
    format of key value pair. They are enclosed in curly brackets
    **{}.**

  - Multiple documents with single streams are separated with 3 hyphens
    **(---)**.

  - Repeated nodes in each file are initially denoted by **(&)** and by
    an asterisk **(\*)** mark later.

  - YAML always requires colons and commas used as list separators
    followed by space with scalar values.

  - Nodes should be labelled with an exclamation mark **(\!)** or double
    exclamation mark **(\!\!)**, followed by string which can be
    expanded into a URL.
