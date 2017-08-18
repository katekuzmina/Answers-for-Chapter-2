
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

## _Question 8_
Define a conditional frequency distribution over the Names corpus that allows you to see which initial letters are more frequent for males vs. females
```python
from nltk.corpus import names
names = nltk.corpus.names
names.fileids()
    [u'female.txt', u'male.txt']
cfd = nltk.ConditionalFreqDist(
    (fileid, name[0])
    for fileid in names.fileids()
    for name in names.words(fileid))
cfd.plot()
data:image/png;base64,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HXdgsViYMWMGU6dO5Y477vDq+D//+c8cf/zxLFy4kGOOOcbtmFdffZVnn32WmTNnMnXqVKcjfMmSJfzpT38CNHPWrl27nE7qn/zkJzz44IOMGjWKZ599lptvvpnOzk6uuOIK/v73vzN79mzlpA4HSuu7oxb2VLWwYEJMP6MV4YbNLtlVqQmI+eMyWLO3htoWJSDCneLiYuf2k08+2eO9trY2rrnmGq655hq3413fu/HGG7nxxhuPMnvdddddzu2CggKWL19+1DkuuugiLrroIgDS09OdWgLA97//fef2nDlz2LhxI7GxsSxYsECFuYYTZS4CYrfjQqKIHA7VttFutjEqJZaJ2UmA0iAUkYkSEAHAVYPYpQRExLHT4aCemptCZqJWbrm2xTyUS1IoAoISEAGgrKHDub27MjDOI8XQofsfpo5KJjNRMx8qJ7UiElE+iADgqkEUVbdgttqJNilZHCnoJTamjUpx/l+VgFBEIuqq5Wc6zDZqWrqINhrITjBisUkO1LQO9bIUfkJK2S0gclPISlIahCJyUQLCz5Q1aNrD6LQ4ClI1BU05qiOH8oYOmjutZCREk50c42JiUj4IReShBISfKa3TBMSY9HjyUrU+sEpARA6uDmohBOkJ0RiA+jYzFpsq2jdcWbNmDRdccIHH4xsbG3n88ccHHOdpRddAMSwFxIffVvLj5zayprhj4MFeovsfxqbHk5+iaxDKUR0p6BVcp41KBsBoECTFaD+j+jalRSg8QwmIEKaquZPP9tWwv97/ncB6CAgXE5Oetq8Ib5waxKgU576UWEc2tUqWC2uKi4s55phjuOaaa5g4cSJXXXUVq1evZsGCBcycOZONGzeyceNGTjjhBGbPns2JJ57I3r17j5qnra2N6667jlNPPbVHuXBXbrvtNg4cOMCsWbO49dZbeffddzn//PORUlJZWcnEiRMpLS09quR3sBmWUUzjMrXsxooWq9/n1pPkxqTHkdlpJCnWRF2bmZqWLkYkq2Ju4c4OR4jrtNxk577UGAOlKEe137grBW/L7nk0/q6mAYcUFRXx9ttv89xzz3Hcccfx2muvsW7dOt566y3++te/8tJLL/H5559jMplYvXo1f/jDH/jf//7XY457772XM844g0cffRSLxcK8efNYuHBhj6zq+++/nx07dvQo2Pfmm2/y73//m+XLl3P33Xcz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
