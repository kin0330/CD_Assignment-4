# Christmas Story Analysis with spaCy
 
## Corpus
This corpus contains three English books that were obtained from Project Gutenberg, specifically from the Children's Book section with the theme of Christmas. I'm curious to discover the primary settings for the events in children's Christmas books.

I used the requests function in pandas to retrieve these books. You can access the original text of the books, namely *[Christmas Eve](https://www.gutenberg.org/ebooks/6670)*, *[The Christmas Child](https://www.gutenberg.org/ebooks/20453)*, and *[The Christmas Dinner](https://www.gutenberg.org/ebooks/14508)*, by following the provided links. 

It's important to note that these books are in the public domain, and you can refer to the **LICENSE** file for more information.

## Process
I employed spaCy, an NLP tool, to extract linguistic information like lemmas, part-of-speech tags, and named entities for text-processing tasks. 

* text preprocessing to delete any unnecessary spaces
* defined the *process_text* function, which applies the nlp pipeline to the provided input text and generates a Doc object for each book. This is where spaCy takes care of all the parsing and tagging tasks
* defined the *get_token* function to obtain a tokenized representation of each book. This means that words, spaces, and punctuation marks are all treated as separate tokens and returned as a list
* defined the *get_lemma* function to retrieve the base form of words. For example, when counting the verb "celebrate," we also consider related forms like "celebrated" and "celebrating." This approach enhances the precision of our analysis by reducing noise
* defined the *get_pos* function to obtain both the general and specific part-of-speech information for each token, which includes *token.pos* and *token.tag*. This information is determined by the chosen language model, in this case, the English model *en_core_web_sm*
* in order to identify locations, we need to extract nouns. Therefore, I defined the extract_proper_nouns function
* however, the resulting list can be quite lengthy, making it challenging to obtain quick results. To address this, we introduce the *extract_named_entities* function, which allows us to visualize the tagging of named entities within a single book
* download enriched dataset which you can find in the CSV file

## Findings
We can now easily pinpoint the locations mentioned in these Christmas stories. It appears that the majority of settings are in Western Counties, specifically in this instance, the United States and the United Kingdom.

Although the corpus in this repository is restricted in size, it confirms that spaCy is a possible NLP tool capable of proficiently parsing (analyzing sentence structure) and tagging (labeling) when studying text collections.

What's more, it's important to keep in mind that relying solely on spaCy may not always provide precise and efficient results. For example, in the case of Named Entities, it incorrectly labeled the phrase *Project Gutenberg* as a PERSON. This could be due to the fact that the phrase has two parts starting with uppercase letters, which may resemble names with a first name and last name.


## About Project Gutenberg
Project Gutenberg is a project to collect and archive public domain texts and is the source of this book. Find out more at their [website](https://www.gutenberg.org/).

>Project Gutenberg (PG) is a volunteer effort to digitize and archive cultural works, to "encourage the creation and distribution of eBooks". It was founded in 1971 by Michael S. Hart and is the oldest digital library. Most of the items in its collection are the full texts of public domain books. The project tries to make these as free as possible, in long-lasting, open formats that can be used on almost any computer. As of July 2012, Project Gutenberg claimed over 40,000 items in its collection. --From [Wikipedia](https://en.wikipedia.org/wiki/Project_Gutenberg), the free encyclopedia

