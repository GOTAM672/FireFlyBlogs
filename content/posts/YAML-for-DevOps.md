---
title: "YAML Basics for DevOps"
date: 2023-06-20T02:34:10+05:30
draft: false

authors: []
description: ""
license: ""
images: []

tags: [DevOps]
categories: []
series: []
series_weight: 1


seriesNavigation: true
featuredImage: "yaml.webp"
featuredImagePreview: "yaml.webp"

hiddenFromHomePage: false
hiddenFromSearch: false
twemoji: false
lightgallery: true
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
linkToSource: false
linkToEdit: false
linkToReport: false
rssFullText: true
license: ''

toc:
  enable: true
  auto: true
code:
  copy: true
  # ...
table:
  sort: true
  # ...
math:
  enable: true
  # ...
mapbox:
  accessToken: ""
  # ...
share:
  enable: true
  # ...
comment:
  enable: true
  # ...
library:
  css:
    # someCSS = "some.css"
    # located in "assets/"
    # Or
    # someCSS = "https://cdn.example.com/some.css"
  js:
    # someJS = "some.js"
    # located in "assets/"
    # Or
    # someJS = "https://cdn.example.com/some.js"
seo:
  images: []
  # ...
outdatedArticleReminder:
  enable: false
  # ...
sponsor:
  enable: false
  # ...
related:
  enable: false
  count: 5

---
### Introduction

YAML stands for `YAMl Ain't Markup Language` and It is not a `programming language`. It is a simple, text-based, human-readable, and `data serialization` language used to exchange data between people and computers just like XML, and JSON.
The file extension for YAML files is `.yaml` or `.yml`.

### What is Data Serialization?

<b>Data serialization</b> is the process of converting data into a format that can be easily stored or sent over a network. It involves converting a data object, which is a combination of code and data, into a series of bytes that represent the object's state in a format that is easily transmittable. The reverse of this process is called data deserialization.

### Why YAML?

- Simple and easy to read.
- It has a strict syntax.
- Easily convertible to JSON, XML.
- Most languages use it.
- More powerful when representing complex data.

### YAML Use Cases in DevOps

It helps in writing configuration files, logs, caches, etc.

- `Docker Compose`: YAML helps in writing the docker-compose.yml file to define multi-container applications.
- `Infrastructure Provisioning`: YAML helps in describing infrastructure resources and their configurations. YAML allows us to define infrastructure components, such as servers, networks, and load balancers, along with their desired state and properties.
- `CI/CD Pipelines`: YAML is used to define CI/CD pipelines in tools like Jenkins, GitLab CI/CD, and CircleCI.

And many more...

### YAML Format Comparison to Others

![](syntax.png)

The data structures in XML and JSON are define using `< >` , and `{ }` respectively. But in YAML `line indentation` and `line separation` are used to define data structures.

### YAML Syntax

This section will provide a basic overview of correct YAML syntax.

#### key-value pairs

Key-value pairs are represented using a `colon (:)` to separate the key and value.

```
name: Gotam Gorabh
college: IIIT Kottayam
degree: BTech
age: 22
current_year: 3
```
#### Comments

Comments can be added using the `#` symbol. Anything after the `#` symbol on a line is considered a comment and is ignored by the parser. It help to make file more readable.

```
# This is a comment
name: Gotam Gorabh
college: IIIT Kottayam
degree: BTech
age: 22
current_year: 3 # Semester 6
```
#### Object

In the below example, `student` is the key representing the object, and the associated value is another set of key-value pairs representing the properties of the student. 

```
student:
  name: Gotam Gorabh
  college: IIIT Kottayam
  degree: BTech
  age: 22
  current_year: 3
```
#### Lists

There are different type of lists in yaml.  

<b>Simple Lists</b>
```
- New Delhi
- Patna
- Kochi
```
<b>Block Lists</b>
```
cities:
  - New Delhi
  - Patna
  - Kochi
```
<b>Compact Block Lists</b>
```
cities: 
  [New Delhi, Patna, Kochi]
```
<b>Inline Lists</b>
```
cities: [New Delhi, Patna, Kochi]
```
<b>Mapping Lists</b>
```
people:
  - name: xyz
    age: 30
  - name: lmn
    age: 25
  - name: opq
    age: 40

```

#### Datatypes

<b>Strings</b>
```
Name : Gotam Gorabh
Collage : "IIIT"
Job : 'Student'
Degree : !!str BTech   # explicit declaration
```
YAML also allow to store multiline data.

```
# Multiline
Bio : |
I am software engineer .
I live in india.

# Singleline
Message : >
This wiil
all be
in single line.
```

<b>Numbers</b>

```
# Integers
Zero : 0
PositiveNumber : 42
NegativeNumber : -43
BinaryNumber : 0b11001
OctalNumber : 06457
Hexa : x45
CommaValue : +540_000  # 540,000
```
```
# Floating
Simple : 74.59
infinite : .inf
Not a Num : .nan
```
```
# Exponential
Number : 6.023E56
```
YAML automatically detects datatype. YAML also provides mechanisms to explicitly specify data types.

```
# Integers
Number : !!int 89

# Floating
Number : !!float 74.59

```

<b>Booleans</b>

```
# Boolean
On : True
Off : False

# explicit declaration
On : !!bool True
Off : !!bool False
```

<b>Null</b>

```
middle_name : !!null Null
```

#### Advanced Datatypes

<b>Sequences (!!seq)</b>  

In YAML, the !!seq tag is used to represent sequences or lists of items. The `!!seq` tag is an optional explicit tag that indicates the sequence data type.

```
fruits: !!seq
  - apple
  - banana
  - orange
```
Some time a sequence (or list) contains gaps or missing elements known as `sparse sequence`.

```
sparse_sequence:
  - apple
  - # This is an empty element or a gap
  - banana
  - # Another empty element or a gap
  - orange
```
We also have `Nested Sequence`.
```
# Nested Sequence
Animal Species : 
  -
    - Tiger
    - Lion
    - Jaguar
  -
    - crow
    - parrot
    - maina
```
<b>Set (!!set)</b>  

The `!!set` tag is used to represent a set data structure. A set is an unordered collection of unique elements, where each element appears only once. The `!!set` tag is an optional explicit tag that indicates the set data type.

```
names : !!set
  ? gautam
  ? suman
  ? himanshu
  ? anshu
  ? roshan
  ? mausham
```
<b>Dictionary (!!omap)</b>  

The `!!omap` tag is used to represent an ordered mapping, which preserves the order of the key-value pairs. The `!!omap` tag stands for "ordered map." 

```
People : !!omap
  - student1 :
      name : Gautam
      roll : 173
  - student2 :
      name : Aman
      roll : 175
```
<b>Anchors</b>  

An anchor is a feature that allows you to create a reference to a specific node in the YAML document. 
Anchors are useful for `reusing or referencing` the same data at multiple points within the document. 
Anchors are denoted using an `ampersand (&)` followed by the anchor name, and references to anchors are denoted using an `asterisk (*)` followed by the anchor name.

```
likings : &likes             
  fav fruit : mango
  dislikes : grapes

person1 :
  name : x 
  << : *likes

```
In the above example, the `likings` key represents an anchor labeled `likes`. It contains `fav fruit` and `dislikes` properties. 
The `person1` keys reuse the same data by using the `<< merge` key, followed by the anchor reference `*likes`. So by doing this, now `person1` has `name`,`fav fruit`, and `dislikes` properties.

We can also override some properties.

```
likings : &likes             
  fav fruit : mango
  dislikes : grapes

person3 : 
  name : z
  << : *likes
  dislikes : papaya    # overriding dislikes

```
 
### Some Useful Tools

Because YAML is so sensitive about the spaces and indentation, these tools will help you to check correctness of a yaml file. 

- [YAMLlint](https://www.yamllint.com/) - Tools to check weither yaml code is valid or not.<br>
- [yaml to jason converter](https://onlineyamltools.com/convert-yaml-to-json) - To generate JASON code from YAML code.<br>
- [datree](https://www.datree.io/) - To validate yaml and kubernetes configuration files.<br>
- [monokle](https://monokle.io/) - Helps in managing kubernetes manifest files.<br>
- [LENS](https://k8slens.dev/) - The kubernetes IDE

