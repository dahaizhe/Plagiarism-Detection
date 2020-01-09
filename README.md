# Plagiarism Detection System
This is a Django Web application for detecting plagiarism in student homework.

## Background

With the rapid development of information technology, students nowadays can easily get access to an enormous amount of data. This could be greatly beneficial for their own literary or academic study. But on the other hand, this could also lead to a more frequent occurrence of plagiarism. <br/>

Compared to the field of academic researches, where practitioners tend to have a high moral standard, plagiarism is more likely to happen in our daily student life. For example, some students would plagiarize in their essays because they run out of ideas or they simply want to get a better grade. Plagiarism like this is unfair to the other honest students and it will inevitably distort the competition. Hence, it would be very helpful if there is an automated way to curb plagiarism in student homework.

## Descriptions

By default, this system groups users into two categories: teachers and students. Since teachers are in charge of the supervision of students' homework, we grant teachers a higher level of authorization and thus more functionalities.

As for the storage structure of homework files, we organize homework text files under different assignment topics. For example, a teacher can create a "Chapter 3 - Newton's Method" folder and all homework files uploaded regarding this topic are stored into that folder.

### Functionalities for Teachers

- Teachers are able to manage all student accounts, including activating accounts or moving accounts into the blacklist.
- Teachers can search, modify or delete any text files under his assignment topics.
- Teachers can perform a plagiarism detection check based on text similarity calculation.
- If the text similarity between two text files are greater than a threshold, a spot of plagiarism is found. Teachers can go on and take a look inside the similar sentences which are marked out in these files.

### Functionalities for Students

- Students can upload their homework text files under an assignment topic.
- Students can modify or delete their homework files.

### Plagiarism Detection Algorithms

#### Bag-of-words Model

Bag-of-words Model, a.k.a. Space Vector Model, is one of the simplifying way for the computers to represent or store text data. In this model, a text is represented as the bag (multiset) of its words, disregarding grammar and even word order but keeping multiplicity. With this representation, we can easily transfer a text into a high-dimensional vector, which facilitates a subsequent calculation of text similarities.

#### Cosine Similarity

Cosine similarity is a measure of similarity between two non-zero vectors of an inner product space that measures the cosine of the angle between them. The cosine similarity is particularly used in positive space, where the outcome is neatly bounded in [0, 1]. These bounds apply for any number of dimensions, and the cosine similarity is most commonly used in high-dimensional positive spaces. For example, in information retrieval and text mining, each term is notionally assigned a different dimension and a document is characterised by a vector where the value in each dimension corresponds to the number of times the term appears in the document. Cosine similarity then gives a useful measure of how similar two documents are likely to be in terms of their subject matter.

#### Jaccard Similarity

Jaccard similarity is a statistic used for gauging the similarity and diversity of sample sets. The Jaccard coefficient measures similarity between finite sample sets, and is defined as the size of the intersection divided by the size of the union of the sample sets. If we treat the words from the sentences as sample sets, we can calculate a similarity bounded in [0, 1], where a statistic near 0 indicates a less similarity while a statistic near 1 means that they are more similar between each others.

## Tools Used
#### Python 3
Python is an interpreted, high-level, general-purpose programming language. As a dynamically typed language, Python is more flexible and it encourages problem solving with different methods. Additionally, Python is more error-tolerant when minor mistakes occur.

*[Learn More](https://www.python.org/)*

#### Django
Django is a Python-based free and open-source web framework, which follows the model-template-view (MTV) architectural pattern. It encourages rapid development and pragmatic design with a support to avoid common security problems.

*[Learn More](https://www.djangoproject.com/)*

#### Bootstrap
Bootstrap is a free and open-source CSS framework directed at responsive, mobile-first front-end web development. It also provides an easy and userful set of rules on grids and layouts operations.

*[Learn More](https://getbootstrap.com/)*

#### SQLite 3
SQLite is a C-language library that implements a small, fast, self-contained, high-reliability, full-featured, SQL database engine. The SQLite file format is stable, cross-platform, and backwards compatible.

*[Learn More](https://www.sqlite.org/index.html)*

The backend logic is built under MVT pattern of Django, in which M(model) acts as the class abstraction of data tables in the database, T(template) is used to form a readable display of information and V(view) takes charge of the process of assigning the client requests to the specific rendering HTML template.

As for the frontend, Bootstrap makes sure it is easy and friendly for users to visualize the similar part of the text segments and the exact numbers of similar text portions.
