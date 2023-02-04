# Predicting-Fake-News-Using-NLP

#Installing NLTK
NLTK requires Python versions 3.7, 3.8, 3.9, 3.10 or 3.11.

For Windows users, it is strongly recommended that you go through this guide to install Python 3 successfully https://docs.python-guide.org/starting/install3/win/#install3-windows

Setting up a Python Environment (Mac/Unix/Windows)
Please go through this guide to learn how to manage your virtual environment managers before you install NLTK, https://docs.python-guide.org/dev/virtualenvs/

Alternatively, you can use the Anaconda distribution installer that comes “batteries included” https://www.anaconda.com/distribution/

# Mac/Unix
Install NLTK: run pip install --user -U nltk

Install Numpy (optional): run pip install --user -U numpy

Test installation: run python then type import nltk

For older versions of Python it might be necessary to install setuptools (see https://pypi.python.org/pypi/setuptools) and to install pip (sudo easy_install pip).

# Windows
These instructions assume that you do not already have Python installed on your machine.

32-bit binary installation
Install Python 3.8: https://www.python.org/downloads/ (avoid the 64-bit versions)

Install Numpy (optional): https://numpy.org/install/

Install NLTK: https://pypi.python.org/pypi/nltk

Test installation: Start>Python38, then type import nltk

Installing Third-Party Software
Please see: https://github.com/nltk/nltk/wiki/Installing-Third-Party-Software

Installing NLTK Data
After installing the NLTK package, please do install the necessary datasets/models for specific functions to work.

If you’re unsure of which datasets/models you’ll need, you can install the “popular” subset of NLTK data, on the command line type python -m nltk.downloader popular, or in the Python interpreter import nltk; nltk.download('popular')

For details, see https://www.nltk.org/data.html

# Natural Language Toolkit
NLTK is a leading platform for building Python programs to work with human language data. It provides easy-to-use interfaces to over 50 corpora and lexical resources such as WordNet, along with a suite of text processing libraries for classification, tokenization, stemming, tagging, parsing, and semantic reasoning, wrappers for industrial-strength NLP libraries, and an active discussion forum.

Thanks to a hands-on guide introducing programming fundamentals alongside topics in computational linguistics, plus comprehensive API documentation, NLTK is suitable for linguists, engineers, students, educators, researchers, and industry users alike. NLTK is available for Windows, Mac OS X, and Linux. Best of all, NLTK is a free, open source, community-driven project.

NLTK has been called “a wonderful tool for teaching, and working in, computational linguistics using Python,” and “an amazing library to play with natural language.”

Natural Language Processing with Python provides a practical introduction to programming for language processing. Written by the creators of NLTK, it guides the reader through the fundamentals of writing Python programs, working with corpora, categorizing text, analyzing linguistic structure, and more. The online version of the book has been been updated for Python 3 and NLTK 3. (The original Python 2 version is still available at https://www.nltk.org/book_1ed.)

# Some simple things you can do with NLTK
Tokenize and tag some text:

>>> import nltk
>>> sentence = """At eight o'clock on Thursday morning
... Arthur didn't feel very good."""
>>> tokens = nltk.word_tokenize(sentence)
>>> tokens
['At', 'eight', "o'clock", 'on', 'Thursday', 'morning',
'Arthur', 'did', "n't", 'feel', 'very', 'good', '.']
>>> tagged = nltk.pos_tag(tokens)
>>> tagged[0:6]
[('At', 'IN'), ('eight', 'CD'), ("o'clock", 'JJ'), ('on', 'IN'),
('Thursday', 'NNP'), ('morning', 'NN')]
Identify named entities:

>>> entities = nltk.chunk.ne_chunk(tagged)
>>> entities
Tree('S', [('At', 'IN'), ('eight', 'CD'), ("o'clock", 'JJ'),
           ('on', 'IN'), ('Thursday', 'NNP'), ('morning', 'NN'),
       Tree('PERSON', [('Arthur', 'NNP')]),
           ('did', 'VBD'), ("n't", 'RB'), ('feel', 'VB'),
           ('very', 'RB'), ('good', 'JJ'), ('.', '.')])
Display a parse tree:

>>> from nltk.corpus import treebank
>>> t = treebank.parsed_sents('wsj_0001.mrg')[0]
>>> t.draw()
_images/tree.gif
NB. If you publish work that uses NLTK, please cite the NLTK book as follows:

Bird, Steven, Edward Loper and Ewan Klein (2009), Natural Language Processing with Python. O’Reilly Media Inc.

