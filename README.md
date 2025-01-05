# WebScraper-W2A test sites

## Overview 
This repository contains a simple set of HTML pages designed as a testing environment for the Web2AI web scraper. The test site includes multiple pages with links, images, and downloadable files (e.g., PDFs) to evaluate scraper functionalities.

The repository provides a controlled setup for testing and debugging of the scraper. Key functionalities to verify include:
* Context-based data filtering.
* Recursive link traversal across multiple pages.
* Extraction of images and downloadable files (e.g., PDFs).
* Integration with ChromaDB for data storage and retrieval.

## Setup
To use these pages as a test site for the **Web2AI scraper**, set up a local web server.

### Starting a local server
Run the following command in the repository's main directory:
```
python -m http.server 5500
```
Prerequisites:
* `Python3` with `http.server` module (pre-installed).


## Usage
To scrape the test site using the Web2AI scraper running in Docker:
1. Start the scraper.
2. Use the following URL as the starting point:
```
http://host.docker.internal:5500
```

## Expected results
After successfully scraping the test site (which should take only a few seconds), the following results are expected:

* Page `host.docker.internal:5500/`:
  * Parent URL: set to `None`
  * Attachments: None
  * Content: *Context* section, links and headers
* Page `host.docker.internal:5500/page2.html`:
  * Parent URL: *host.docker.internal:5500/*
  * Attachments: two images, one pdf
  * Content: *Relevant Data* section, headers, link to main page, link to PDF file
* Page `host.docker.internal:5500/page3.html`:
  * Parent URL: *host.docker.internal:5500/*
  * Attachments: one image
  * Content: *Relevant Data* section, headers, link to main page

## Structure
The repository has following structure:
```
test-site/
├── index.html         # Main page linking to other pages.
├── page2.html         # Second page with images, data, and a PDF link.
├── page3.html         # Third page with images and data.
├── README.md          # Documentation for the repository.
├── LICENSE            # License file.

```

## Note
All images and PDF files included in this repository are sourced from **https://www.pcss.pl/do-pobrania/**.

## License
This project is licensed under the [Apache 2.0](LICENSE) License.