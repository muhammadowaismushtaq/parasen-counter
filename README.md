# ParaSen Counter

> Creation Date: December 29, 2019

## Project Description

**ParaSen Counter** is a console-based C++ application designed to analyze textual data from input files. It processes documents such as research papers, articles, and essays to:

* Count **alphabets, words, and sentences**
* Store and manage multiple files dynamically
* Allow users to **search sentences by index**
* Provide **file-wise analysis** and **aggregate (average) statistics**

The system uses custom-built data structures (Linked Lists and Queues) instead of STL to demonstrate core **Data Structures & Algorithms (DSA)** concepts.

> For detailed workflow and design explanation, refer to the [Project Report](https://github.com/muhammadowaismushtaq/ParaSen-Counter/blob/99ba99f398f9eb33bfa907a9e29628df0bfd34a3/Project%20Report.pdf)

---

## Core Features

* Insert and process multiple `.txt` files
* Count:

  * Alphabets
  * Words
  * Sentences
* Search any sentence by its position
* View:

  * Individual file statistics
  * Average statistics across all inserted files
* Custom implementation of:

  * Singly Linked List
  * Queue (via Linked List)

---

## Data Structures Used

### 1. **SentenceList (Singly Linked List)**

* Stores **sentences of a single file**
* Each node contains:

  * One sentence (string)
* Used for:

  * Efficient sentence storage
  * Indexed sentence retrieval (`SearchSentence` feature)

---

### 2. **Template Singly Linked List (`sll`)**

* Generic implementation used as a base structure
* Supports:

  * Insertions (head, tail, index)
  * Deletions
  * Traversal

---

### 3. **Queue (`sll_queues`)**

* Built on top of the template linked list
* Stores **File objects dynamically at runtime**

Purpose:

* Maintain multiple uploaded files
* Enable sequential processing (FIFO)

---

### 4. **File Class**

Each file is encapsulated as an object containing:

* File name
* Alphabet count
* Word count
* Sentence count
* A `SentenceList` storing all sentences

---

## Dataset Used

### Input Dataset

* The application uses **user-provided `.txt` files as dataset**
* Examples:

  * Articles
  * Essays
  * Research papers
  * Any plain text document

---

## Where & Why Dataset is Used

### 1. **File Insertion (`FileInsertion()` function)**

* Reads the entire `.txt` file character by character
* Stores content in a string
* Performs:

  * Sentence segmentation
  * Word counting
  * Alphabet counting

**Why?**
To preprocess raw textual data into structured form for analysis.

---

### 2. **Sentence Extraction**

* Sentences are identified using delimiters:

  * `.`, `!`, `?`, `;`
* Each sentence is inserted into `SentenceList`

**Why?**
To enable efficient **sentence-level access and search**

---

### 3. **Statistical Analysis (`Analysis()` function)**

* Uses all inserted file datasets
* Computes:

  * Per-file statistics
  * Average statistics across all files

**Why?**
To provide insights across multiple documents

---

### 4. **Search Functionality (`SearchSentence()` function)**

* Retrieves a sentence by index from a selected file

**Why?**
To allow quick lookup without scanning entire text again

---

## Design Approach

* Avoided STL to **manually implement DSA concepts**
* Modular design:

  * File handling
  * Data storage
  * Processing
* Queue ensures **multi-file management**
* Linked list ensures **dynamic memory usage**

---

## How to Run

1. Compile using a C++ compiler (Windows environment recommended due to `conio.h` and `windows.h`)
2. Run the program
3. Use menu:

   * Add File
   * Analysis
   * Search Sentence

---

## Limitations

* Works only with `.txt` files
* Sentence detection is **basic (delimiter-based)**
* Windows-specific (due to console handling libraries)
* No punctuation/context-aware NLP

---

## Author

**Muhammad Owais Mushtaq**
[LinkedIn](https://www.linkedin.com/in/muhammadowaismushtaq)
