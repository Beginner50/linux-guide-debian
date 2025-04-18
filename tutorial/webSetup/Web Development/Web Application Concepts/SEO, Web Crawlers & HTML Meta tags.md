## Search Engine Optimization
Search Engine Optimization (SEO) is the process of optimizing a website to improve its visibility and ranking on search engine result pages (SERPS).

#### How SEO works?
Search engines use algorithms to crawl, index, and rank web pages based on hundreds of factors; some of which are listed below:

- Anticipating keywords or phrases users will search for to look for your website content and placing those keywords meaningfully in your website according to **TF-IDF** algorithm.
- Optimizing the site for various devices (Site **responsiveness**).
- Using **semantic tags** to provide context and readability to both the developer and search engines.
- Using **meta tags** to control search engine web crawler behavior.
- Adding **breadcrumbs** to improve user experience & SEO.
- Submit an **XML sitemap** to search engines to help them discover your pages.

* * *
## TF-IDF Algorithm
### Term Frequency
**TF (Term Frequency)** measures how often a word appears in a document relative to the total number of words in that document.

$$ TF(t,d) = \frac{Number \; of \; times \; t \; appears \; in \; document \; d}{Total \; Number \; of \; terms \; in \; document \; d}$$

A page that contains more occurrences of a search term will a higher score for that term.

### Inverse Document Frequency
**IDF (Inverse Document Frequency)** measures how important a term is across all documents in the corpus. It decreases the weight of common words (e.g the, a, and) and increases the weight of rare words.

$$ IDF(t) = \log(\frac{Total \; Number \; of \; Documents}{Number \; of \; Documents \; containing \; the \; term \; t}) $$

Terms that are more unique across the web will get a higher IDF score.

### TF-IDF
**TF-IDF** is simply their product

$$TF-IDF(t,d) = TF(t,d) \cdot IDF(t)$$
It gives a weight to each term in the document that reflects both its frequency within the document and its rarity across the entire corpus.


### Potential Flaws in TF-IDF
1) **Keyword Stuffing**: If a website simply adds a high frequency of search query terms, the TF will increase significantly.
2) **Lack of Context**: TF-IDF doesn't understand the context of words.


***
## HTML Meta Tags
HTML Meta tags are used to control web crawlers' behavior as well as improve SEO.

- Use of **title tags**: `<title>`
	Title tags are the clickable headlines on search engine results.
- Meta **description** tag
	`<meta name="description" content="Description of web page">`
- Meta **keywords** tag
	`<meta name="keywords" content="keyword1, keyword phrase, keyword2">`
	Historically, this tag was used to rank web pages but has since been abandoned due to abuse from keyword stuffing.
- Meta **viewport** tag
	`<meta name="viewport" content="width=device-width, initial-scale=1.0">`
	Ensures that your page scales correctly on mobile devices and increase ranking
- Meta **charset** tag 
	`<meta charset="UTF-8">`
	Defines the character encoding for the document, ensuring the correct display of characters.

### Controlling Web Crawlers' behavior
You can use meta tags to control web crawlers' behavior:
1) **Controlling Indexing Behavior**
	`<meta name="robots" content="noindex">`
	This meta tag tells search engine crawlers not to index page on search results.
	
2) **Controlling Link Follow Behavior**
	`<meta name="robots" content="nofollow"`
	This meta tag prevents web crawlers from following specific links on a page.
	