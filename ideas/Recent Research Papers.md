
# Analysis of Research paper metadata

See what are some really influential papers of the recent years (post 2000, 2010 etc.)

Build a graph where nodes are papers, edges are references/citations.

Some clusters would form: bitcoin, blockchain, machine-learning etc.
    - Some papers would cross clusters 

A dynamic timeline which filters papers past dates

## What are we looking for?

* To which fields do the recent top 50 papers belong to?

```sql
SELECT paper_name, author_name
FROM papers
WHERE year(pub_date) > 2000
ORDER BY citation_count DESC
LIMIT 50
```

## Data Sources

* Readymade datasets
    - https://www.aminer.cn/citation
    - http://opencitations.net/download

* Scholar Wikidata
* Google Scholar
* Microsoft Scholar Data?

### Scraping Google Scholar

* https://github.com/fnielsen/scholia
    - Deals with WikiData

* https://harzing.com/resources/publish-or-perish
    - A desktop app that parses google scholar data somehow

* https://github.com/ckreibich/scholar.py
    - Last updated years ago
    - Probably won't work

* https://www.nature.com/articles/d41586-018-04190-5
* https://mystudentvoices.com/scraping-google-scholar-to-write-your-phd-literature-chapter-2ea35f8f4fa1
* http://lintool.github.io/scholar-scraper/

## Technologies Involved

* Python
    - Jupyter Notebooks

* Data Processing & Analysis
    - How do you even deal with large amounts of data?
    - Use standard unix tools & pipelines to process

* Visualisations
    - HTML/CSS
    - d3.js
        + For creating plots etc.

* Single machine Hadoop/Spark setup?
* Use pandas (or other pydata tools?)
