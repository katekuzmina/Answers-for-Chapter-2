
# Natural Language Processing with Python 
## Answers for Chapter 2 

## _Question 1_

Create a variable phrase containing a list of words. Review the operations described in the previous chapter, including addition, multiplication, indexing, slicing, and sorting.


```python
phrase = ['The', 'ended', 'beginner', 'shines', 'before', 'a', 'house']
phrase_add = phrase + ['!']
phrase_add 
    ['The', 'ended', 'beginner', 'shines', 'before', 'a', 'house', '!']
phrase_mul = phrase*2
phrase_mul
    ['The',
     'ended',
     'beginner',
     'shines',
     'before',
     'a',
     'house',
     'The',
     'ended',
     'beginner',
     'shines',
     'before',
     'a',
     'house']
phrase_ind = phrase[3]
phrase_ind
    'shines'
pharse_sli = phrase[:-2]
pharse_sli 
    ['The', 'ended', 'beginner', 'shines', 'before']
phrase_sort = sorted(w.lower() for w in phrase)
phrase_sort
    ['a', 'before', 'beginner', 'ended', 'house', 'shines', 'the']
```
## _Question 2_

Use the corpus module to explore austen-persuasion.txt. How many word tokens does this book have? How many word types?

```python
import nltk
from nltk.corpus import gutenberg
gutenberg.fileids()[:5]
    [u'austen-emma.txt',
     u'austen-persuasion.txt',
     u'austen-sense.txt',
     u'bible-kjv.txt',
     u'blake-poems.txt']
persuasion_tokens = gutenberg.words('austen-emma.txt')
len(persuasion_tokens)
    192427
persuasion_wt = sorted(set(w.lower() for w in persuasion_tokens))
len(persuasion_wt)
    7344
```

## _Question 3_

Use the Brown corpus reader nltk.corpus.brown.words() or the Web text corpus reader nltk.corpus.webtext.words() to access some sample text in two different genres.


```python
from nltk.corpus import brown
brown.words()
    [u'The', u'Fulton', u'County', u'Grand', u'Jury', ...]
brown.categories()
    [u'adventure',
     u'belles_lettres',
     u'editorial',
     u'fiction',
     u'government',
     u'hobbies',
     u'humor',
     u'learned',
     u'lore',
     u'mystery',
     u'news',
     u'religion',
     u'reviews',
     u'romance',
     u'science_fiction']
print brown.sents(categories ='adventure')[2:3]
    [[u'He', u'certainly', u"didn't", u'want', u'a', u'wife', u'who', u'was', u'fickle', u'as', u'Ann', u'.']]
print brown.sents(categories = 'romance')[2:3]
    [[u'The', u'Old', u'Man', u'was', u'unimportant', u'.']]
```

## _Question 4_

Read in the texts of the State of the Union addresses, using the state_union corpus reader. Count occurrences of men, women, and people in each document. What has happened to the usage of these words over time?


```python
from nltk.corpus import state_union
state_union.fileids()
    [u'1945-Truman.txt',
     u'1946-Truman.txt',
     u'1947-Truman.txt',
     u'1948-Truman.txt',
     u'1949-Truman.txt']
cfd = nltk.ConditionalFreqDist(
        (target, fileid[:4])
        for fileid in state_union()
        for w in state_union.words(fileid)
        for target in ['men', 'women', 'people']
        if w.lower().startswith(target))

    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-155-1bd1c61ff83e> in <module>()
          1 cfd = nltk.ConditionalFreqDist(
          2         (target, fileid[:4])
    ----> 3         for fileid in state_union()
          4         for w in state_union.words(fileid)
          5         for target in ['men', 'women', 'people']


    TypeError: 'PlaintextCorpusReader' object is not callable
```
## _Question 5_

Investigate the holonym-meronym relations for some nouns. Remember that there are three kinds of holonym-meronym relation, so you need to use: member_meronyms(), part_meronyms(), substance_meronyms(), member_holonyms(), part_holonyms(), and substance_holonyms().


```python
from nltk.corpus import wordnet as wn
wn.synsets("computer")
    [Synset('computer.n.01'), Synset('calculator.n.01')]
len(wn.synsets("computer"))
    2
wn.synset('computer.n.01').part_meronyms() #components of items
    [Synset('busbar.n.01'),
     Synset('cathode-ray_tube.n.01'),
     Synset('central_processing_unit.n.01'),
     Synset('chip.n.07'),
     Synset('computer_accessory.n.01'),
     Synset('computer_circuit.n.01'),
     Synset('data_converter.n.01'),
     Synset('disk_cache.n.01'),
     Synset('diskette.n.01'),
     Synset('hardware.n.03'),
     Synset('keyboard.n.01'),
     Synset('memory.n.04'),
     Synset('monitor.n.04'),
     Synset('peripheral.n.01')]
wn.synset('computer.n.01').substance_meronyms() #components of items
    []
wn.synset('computer.n.01').member_holonyms() #things in which items are contained
    []
wn.synsets("man")
    [Synset('man.n.01'),
     Synset('serviceman.n.01'),
     Synset('man.n.03'),
     Synset('homo.n.02'),
     Synset('man.n.05'),
     Synset('man.n.06'),
     Synset('valet.n.01'),
     Synset('man.n.08'),
     Synset('man.n.09'),
     Synset('man.n.10'),
     Synset('world.n.08'),
     Synset('man.v.01'),
     Synset('man.v.02')]
wn.synset('homo.n.02').part_meronyms()
    [Synset('arm.n.01'),
     Synset('body_hair.n.01'),
     Synset('face.n.01'),
     Synset('foot.n.01'),
     Synset('hand.n.01'),
     Synset('human_body.n.01'),
     Synset('human_head.n.01'),
     Synset('loin.n.02'),
     Synset('mane.n.02')]
wn.synset('homo.n.02').substance_meronyms()
    []
wn.synset('homo.n.02').member_holonyms()
    [Synset('genus_homo.n.01')]
```
## _Question 6_

In the discussion of comparative wordlists, we created an object called translate which you could look up using words in both German and Spanish in order to get corresponding words in English. What problem might arise with this approach? Can you suggest a way to avoid this problem?

```python
from nltk.corpus import swadesh
fr2en = swadesh.entries(['fr', 'en'])
translate = dict(fr2en)
translate['chien']
    u'dog'
translate['dog']
    ---------------------------------------------------------------------------
    KeyError                                  Traceback (most recent call last)

    <ipython-input-56-f436b93cc2da> in <module>()
    ----> 1 translate['dog']
    KeyError: 'dog'
```
__ANSWER__: The problem is that we cannot translate from English into other languages. How to solve it - I do not know at this moment.

## _Question 7_

According to Strunk and White's Elements of Style, the word however, used at the start of a sentence, means "in whatever way" or "to whatever extent", and not "nevertheless". They give this example of correct usage: However you advise him, he will probably do as he thinks best. (http://www.bartleby.com/141/strunk3.html) Use the concordance tool to study actual usage of this word in the various texts we have been considering. See also the LanguageLog posting "Fossilized prejudices about 'however'" at http://itre.cis.upenn.edu/~myl/languagelog/archives/001913.html

```python
from nltk.corpus import gutenberg
nltk.corpus.gutenberg.fileids()
text = nltk.Text(gutenberg.words('carroll-alice.txt'))
text.concordance("however")
Displaying 20 of 20 matches:
ate it would not open any of them . However , on the second time round , she ca
sagree with you , sooner or later . However , this bottle was NOT marked ' pois
r into that lovely garden . First , however , she waited for a few minutes to s
 never get to twenty at that rate ! However , the Multiplication Table doesn ' 
nd behind them a railway station .) However , she soon made out that she was in
ILL be a queer thing , to be sure ! However , everything is queer to - day .' J
sy to know when the race was over . However , when they had been running half a
 and had to be patted on the back . However , it was over at last , and they sa
ow - spirited . In a little while , however , she again heard a little patterin
nd this a very difficult question . However , at last she stretched her arms ro
o be , from one minute to another ! However , I ' ve got back to my right size 
ow whether it would like the name : however , it only grinned a little wider . 
n ' t think that proved it at all ; however , she went on ' And how do you know
 !' said the Dormouse indignantly . However , he consented to go on . ' And so 
 , tumbling up against each other ; however , they got settled down in a minute
k of it at all ,' said the King : ' however , it may kiss my hand if it likes .
t was an uncomfortably sharp chin . However , she did not like to be rude , so 
e , and were resting in the shade : however , the moment they saw her , they hu
ght as well be at school at once .' However , she got up , and began to repeat 
age knew the meaning of it at all . However , ' jury - men ' would have done ju
```
__ANSWER__: From this analysis, we can see that Lewis Carroll often used "however" in the sentence-initial position that might be considered innovative and unique for a book written in 1865. 
