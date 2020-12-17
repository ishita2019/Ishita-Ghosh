# Ishita-Ghosh
The notebook file contains the python code for web crawling for common crawl data.
I have tried out different approaches for getting the data. 

The simplest approach I have used is to get the segment file from common crawl for each month as saved it as text file. The each month's segment and WARC files contain the URL for the archive files that may or may not be related to COVID 19 impact on economy.

I have saved this data on a text file and taking the URL one by one to check the archive for it and find out of the stream content includes Covid 19 economy impact.

While doing this, I found 2 strategy could be useful:

1: Regex Search: Using regex it is possible to find out which URL's content contains words like Covid 19 and economy both so that we know it has discussed and covered the topics we are intered in. This the most easy way ato do it.

2: TF-IDF method: This method is usedful for better search when it comes to topic modelling, however since the content of the stream here contains images and many other language text as well in some URL's , I couldn't come up with an compact approach in this limited time to implement and execute the method.

3: Using NLTK and Gensim library: This option is viable and relatively easier than TF-IDF method, but using stemming or lemmatization will be difficult since the content of the streaming is not pure text. Stopwords removing will also include some tactic, whcih is feasible to figure our by experimenting once in a project, due to the time constrains of this assigment I could not experiment with this approach.

I chose to go ahead with Method 1, Regex search. Since this is simple I wrote a code which is reading the WARC file for getting all the URL's from the Archive and in this content through streaming, it is searching the COVID and economy as topic. If those two words are found then it is further going into the content details and searching the number of hit's till end. If the number of hits is more than 1000 times, then we could be confident enough that the URL is not only includes the content that barely uses the words COVID and economoy, rather it is talking about it more frequently. This is basically the same approach as "Term Frequency" but through regex.

I have prepared a list that contains all the URL's we have captured from 2020 January archive and it's WARC file. I have only included the URL's which has the hits more than 1000. 

The major challenge I faced during this exercise is the time this program is taking to execute. Since I kept it simple, even though the script is working, it is taking almost 10 minues time for each URL in the WARC file for the only Janury 2020 archive. Given this timeline, it is not possible to gather more than 1000 such URLs but the method is a working method. 

I have included the WARC file and the jupyter notebook I have been wokring with. 
