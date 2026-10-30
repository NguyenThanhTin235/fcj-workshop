---
title: "Blog 2"
date: 2026-10-05
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

<h2 align="center">AMAZON TEXTRACT – BEYOND BASIC DOCUMENT TEXT EXTRACTION</h2>

During the development of a recruitment system project, finding a solution to extract text from PDF documents was an essential requirement. When researching traditional OCR tools, I noticed that text recognition could face significant limitations, especially with documents having complex layouts, tables, or inconsistent formatting. In several evaluated cases, accuracy only ranged around 70–80%, depending on the tool and input document.

From that need, I learned about Amazon Textract – an AWS Machine Learning service that automatically extracts text and analyzes document structure.

What caught my attention was not just the character recognition capability, but how Textract transforms document content into structured data for downstream application processing.

### 1. CONTEXT AND LIMITATIONS OF TRADITIONAL OCR

Traditional OCR tools approach documents by scanning images and attempting to recognize individual characters line by line. This approach exhibits clear limitations:

* Multi-column documents: Reading order is easily scrambled across columns, altering the original meaning of paragraphs.
* Form-based data: Difficult to distinguish between field labels and the values submitted by users.
* Tabular data: Flattened into continuous text strings, losing relationships between rows and columns.
* Variable layouts: Real-world documents rarely follow a fixed template, causing rigid coordinate-based methods to struggle.

To solve this challenge, Amazon Textract provides an automated approach to document structure analysis without requiring a custom end-to-end preprocessing pipeline.

### 2. OVERVIEW OF AMAZON TEXTRACT

Amazon Textract is an AWS Machine Learning service developed to read and comprehend documents similarly to human inspection.

Unlike basic OCR that only returns raw text strings, Textract analyzes the spatial architecture of documents and returns detailed information on every component: pages, lines, words, key-value pairs, tables, and individual cells. Each element includes its spatial position on the page along with a confidence score for the recognition result.

### 3. KEY FEATURES OF AMAZON TEXTRACT

Textract provides multiple useful features catering to diverse document processing needs:

* **Text Detection:** Detects printed text and handwriting in supported documents and images. The output contains both textual content and spatial location on the page. This capability fits applications needing to digitize documents for search, archiving, or downstream processing.
* **Form Extraction:** A notable capability of Textract is recognizing relationships between field labels and corresponding values, also known as key-value pairs. For example, from a form containing Name: Nguyen Van A, the system identifies Name as the field label and Nguyen Van A as the corresponding value, rather than returning a continuous string.
* **Table Extraction:** Capable of recognizing tables, rows, columns, and cell contents. As a result, structured data within documents is converted into convenient formats for downstream workflows. This feature is particularly helpful when processing reports, invoices, data sheets, and table-heavy documents.
* **Queries:** One of the most compelling capabilities. Instead of requesting the system to parse the entire document, Queries allows specifying target information using natural language questions. For example, on a suitable document, the application can ask questions such as:
  * What is the customer name?
  * What is the invoice date?
  * What is the total amount?
  Textract locates the corresponding information and returns separate results for each query. This helps applications focus directly on needed data without manual post-filtering.
* **Layout and Signature Detection:**
  * Layout: Recognizes structural elements such as titles, paragraphs, lists, tables, and page numbers, preserving document layout information.
  * Signature Detection: Detects signature locations in documents and returns coordinates along with confidence scores. These capabilities expand Textract usage in document verification, profile review, and workflow automation.

### 4. NOTABLE APIS

Amazon Textract provides several APIs for different requirements:

* **DetectDocumentText:** General text recognition.
* **AnalyzeDocument:** Analyzes text, forms, tables, layouts, and queries.
* **AnalyzeExpense:** Extracts data related to invoices and receipts.
* **AnalyzeID:** Extracts information from supported identity documents.
* **Analyze Lending:** Classifies and analyzes loan document packages according to service workflows.

Depending on the use case, applications can choose synchronous processing for quick responses or asynchronous processing for multi-page documents and large workloads.

### 5. PRODUCTION CONSIDERATIONS

Despite its powerful capabilities, Textract does not mean every document is recognized with absolute perfection. Results depend on document quality, language, layout, and target information type.

A useful feature is that Textract returns confidence scores for recognition results, allowing applications to establish validation rules or request manual verification when necessary. However, confidence scores should not be treated as an absolute guarantee of accuracy.

Additionally, applications need to select the appropriate API, verify supported languages and document types, and plan for processing volume costs.

### 6. CONCLUSION

Exploring Amazon Textract during project development broadened my perspective on applying AI and Machine Learning to document processing.

Textract goes beyond OCR by supporting structural recognition, extracting form and table data, answering natural language queries, and handling specialized document types.

This is a valuable service to consider when building applications that automate document reading and processing, especially when integrating these capabilities via managed APIs rather than building a custom recognition pipeline from scratch.

### References

* Amazon Textract Features: [https://aws.amazon.com/textract/features/](https://aws.amazon.com/textract/features/)
* Amazon Textract Developer Guide: [https://docs.aws.amazon.com/textract/latest/dg/](https://docs.aws.amazon.com/textract/latest/dg/)
* Analyzing Documents: [https://docs.aws.amazon.com/textract/latest/dg/how-it-works-analyzing.html](https://docs.aws.amazon.com/textract/latest/dg/how-it-works-analyzing.html)

#AWS #AmazonTextract #OCR #MachineLearning #AI #DocumentProcessing #AWSStudyGroup

Link bài viết: [https://www.facebook.com/share/p/1DTpmyx7i3/](https://www.facebook.com/share/p/1DTpmyx7i3/)
