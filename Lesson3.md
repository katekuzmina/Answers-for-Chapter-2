

```python
import nltk
nltk.download()
from nltk.book import *
# nltk.book.sent1 
```

    showing info https://raw.githubusercontent.com/nltk/nltk_data/gh-pages/index.xml
    *** Introductory Examples for the NLTK Book ***
    Loading text1, ..., text9 and sent1, ..., sent9
    Type the name of the text or sentence to view it.
    Type: 'texts()' or 'sents()' to list the materials.
    text1: Moby Dick by Herman Melville 1851
    text2: Sense and Sensibility by Jane Austen 1811
    text3: The Book of Genesis
    text4: Inaugural Address Corpus
    text5: Chat Corpus
    text6: Monty Python and the Holy Grail
    text7: Wall Street Journal
    text8: Personals Corpus
    text9: The Man Who Was Thursday by G . K . Chesterton 1908



```python
#Using list addition, and the set and sorted operations, compute the vocabulary of the sentences sent1 ... sent8.
len(sent1)+len(sent2)
```




    15




```python
s = sent1 + sent2 + sent3 + sent4 + sent5 + sent6 + sent7 + sent8
```


```python
sorted(set([w.lower() for w in s if w.isalpha()])) # this called list comprehension
```




    ['a',
     'and',
     'arthur',
     'as',
     'attrac',
     'been',
     'beginning',
     'board',
     'call',
     'citizens',
     'clop',
     'created',
     'dashwood',
     'director',
     'discreet',
     'earth',
     'encounters',
     'family',
     'fellow',
     'for',
     'god',
     'had',
     'have',
     'heaven',
     'house',
     'i',
     'in',
     'ishmael',
     'join',
     'king',
     'lady',
     'lol',
     'long',
     'male',
     'me',
     'nonexecutive',
     'of',
     'old',
     'older',
     'people',
     'pierre',
     'pming',
     'problem',
     'representatives',
     'scene',
     'seeks',
     'senate',
     'settled',
     'sexy',
     'single',
     'sussex',
     'the',
     'there',
     'to',
     'vinken',
     'whoa',
     'will',
     'wind',
     'with',
     'years']




```python
#21. Write the slice expression that extracts the last two words of text2.
text2[-2:] # from -2th word till the end
```




    ['THE', 'END']




```python
#22. Find all the four-letter words in the Chat Corpus (text5). 
# With the help of a frequency distribution (FreqDist), show these words in decreasing order of frequency.
four = [w for w in text5 if len(w) == 4]
fdist5 = FreqDist(text5)
f = FreqDist(four)
f.most_common(len(four))
```




    [('JOIN', 1021),
     ('PART', 1016),
     ('that', 274),
     ('what', 183),
     ('here', 181),
     ('....', 170),
     ('have', 164),
     ('like', 156),
     ('with', 152),
     ('chat', 142),
     ('your', 137),
     ('good', 130),
     ('just', 125),
     ('lmao', 107),
     ('know', 103),
     ('room', 98),
     ('from', 92),
     ('this', 86),
     ('well', 81),
     ('back', 78),
     ('hiya', 78),
     ('they', 77),
     ('dont', 75),
     ('yeah', 75),
     ('want', 71),
     ('love', 60),
     ('guys', 58),
     ('some', 58),
     ('been', 57),
     ('talk', 56),
     ('nice', 52),
     ('time', 50),
     ('when', 48),
     ('haha', 44),
     ('make', 44),
     ('girl', 43),
     ('need', 43),
     ('U122', 42),
     ('MODE', 41),
     ('will', 40),
     ('much', 40),
     ('then', 40),
     ('over', 39),
     ('work', 38),
     ('were', 38),
     ('take', 37),
     ('U121', 36),
     ('U115', 36),
     ('song', 36),
     ('even', 35),
     ('does', 35),
     ('seen', 35),
     ('U156', 35),
     ('U105', 35),
     ('more', 34),
     ('damn', 34),
     ('only', 33),
     ('come', 33),
     ('hell', 29),
     ('long', 28),
     ('them', 28),
     ('name', 27),
     ('tell', 27),
     ('away', 26),
     ('sure', 26),
     ('look', 26),
     ('baby', 26),
     ('call', 26),
     ('play', 25),
     ('U110', 25),
     ('U114', 25),
     ('NICK', 24),
     ('down', 24),
     ('cool', 24),
     ('sexy', 23),
     ('many', 23),
     ('hate', 23),
     ('said', 23),
     ('last', 22),
     ('ever', 22),
     ('hear', 21),
     ('life', 21),
     ('live', 20),
     ('feel', 19),
     ('very', 19),
     ('mean', 19),
     ('give', 19),
     ('same', 19),
     ('must', 19),
     ('stop', 19),
     ('LMAO', 19),
     ('!!!!', 18),
     ('hugs', 18),
     ('What', 18),
     ('find', 18),
     ('cant', 18),
     ('left', 17),
     ('????', 17),
     ('shit', 17),
     ('nite', 17),
     ('busy', 17),
     ('hair', 17),
     ('lost', 17),
     ('U104', 17),
     ('fine', 16),
     ('real', 16),
     ('game', 16),
     ('fuck', 15),
     ('sits', 15),
     ('eyes', 15),
     ('lets', 15),
     ('heya', 15),
     ('kill', 15),
     ('read', 14),
     ('shut', 14),
     ('wait', 14),
     ('goes', 14),
     ('keep', 14),
     ('true', 14),
     ('pick', 13),
     ('free', 13),
     ('else', 13),
     ('near', 13),
     ('nope', 13),
     ('U168', 13),
     ('hope', 12),
     ('head', 12),
     ('male', 12),
     ('than', 12),
     ('gets', 12),
     ('cold', 12),
     ('hehe', 12),
     ('bout', 12),
     ('stay', 12),
     ('used', 12),
     ('awww', 12),
     ('told', 12),
     ('This', 12),
     ('U102', 12),
     ('doin', 11),
     ('kids', 11),
     ('perv', 11),
     ('wont', 11),
     ('face', 11),
     ('home', 11),
     ('year', 11),
     ('babe', 11),
     ('into', 11),
     ('yall', 11),
     ('.. .', 11),
     ('U119', 11),
     ('U107', 11),
     ('hard', 10),
     ('show', 10),
     ('U101', 10),
     ('once', 10),
     ('Well', 10),
     ('help', 10),
     ('mind', 10),
     ('Yeah', 10),
     ('week', 10),
     ('Liam', 10),
     ('U132', 10),
     ('pics', 9),
     ('such', 9),
     ('type', 9),
     ('best', 9),
     ('neck', 9),
     ('dang', 9),
     ('dead', 9),
     ('runs', 9),
     ('aint', 9),
     ('rock', 9),
     ('days', 9),
     ('mine', 9),
     ('book', 9),
     ('crap', 9),
     ('soon', 9),
     ('care', 9),
     ('full', 9),
     ('kiss', 9),
     ('hour', 9),
     ('nick', 9),
     ('sick', 9),
     ('; ..', 9),
     ('hmmm', 9),
     ('U139', 8),
     ('word', 8),
     ('heyy', 8),
     ('case', 8),
     ('wana', 8),
     ('hows', 8),
     ('went', 8),
     ('lady', 8),
     ('blue', 8),
     ('says', 8),
     ('suck', 8),
     ('made', 8),
     ('wife', 8),
     ('sang', 8),
     ('U144', 8),
     ('fast', 7),
     ('rule', 7),
     ('dude', 7),
     ('okay', 7),
     ('alot', 7),
     ('hand', 7),
     ('took', 7),
     ('wear', 7),
     ('Hiya', 7),
     ('kick', 7),
     ('ahhh', 7),
     ('dear', 7),
     ('That', 7),
     ('U108', 7),
     ('U169', 7),
     ('U129', 6),
     ('U116', 6),
     ('most', 6),
     ('thru', 6),
     ('U165', 6),
     ('list', 6),
     ('seem', 6),
     ('sing', 6),
     ('next', 6),
     ('done', 6),
     ('ride', 6),
     ('comp', 6),
     ('main', 6),
     ('))))', 6),
     ('goin', 6),
     ('U520', 6),
     ('pink', 6),
     ('poor', 6),
     ('gone', 6),
     ('oops', 6),
     ('knew', 6),
     ('<---', 6),
     ('ball', 6),
     ('send', 6),
     ('Song', 6),
     ('blah', 6),
     ('They', 6),
     ('part', 6),
     ('U103', 6),
     ('U120', 6),
     ('Last', 6),
     ('whos', 6),
     ('food', 6),
     ('U142', 6),
     ('sock', 6),
     ('U197', 6),
     ('legs', 5),
     ('fire', 5),
     ('warm', 5),
     ('late', 5),
     ('hang', 5),
     ('miss', 5),
     ('boys', 5),
     ('land', 5),
     ('nose', 5),
     ('lick', 5),
     ('caps', 5),
     ('wish', 5),
     ('U128', 5),
     ('came', 5),
     ('cali', 5),
     ('roll', 5),
     ('easy', 5),
     ('lose', 5),
     ('When', 5),
     ('soul', 5),
     ('luck', 5),
     ('also', 5),
     ('kool', 5),
     ('fall', 5),
     ('boss', 5),
     ('beer', 5),
     ('ohhh', 5),
     ('####', 5),
     ('wall', 5),
     ('Have', 5),
     ('meet', 5),
     ('till', 5),
     ('feet', 5),
     ('xbox', 5),
     ('idea', 5),
     ('heck', 5),
     ('joke', 5),
     ('fool', 5),
     ('felt', 5),
     ('yoko', 5),
     ('meds', 5),
     ('both', 5),
     ('Lime', 5),
     ('glad', 4),
     ('U133', 4),
     ('U126', 4),
     ('jerk', 4),
     ('ugly', 4),
     ('date', 4),
     ('ummm', 4),
     ('quit', 4),
     ('rest', 4),
     ('door', 4),
     ('none', 4),
     ('self', 4),
     ('pass', 4),
     ('line', 4),
     ('cute', 4),
     ('holy', 4),
     ('hook', 4),
     ('Like', 4),
     ('each', 4),
     ('open', 4),
     ('high', 4),
     ('ouch', 4),
     ('evil', 4),
     ('fart', 4),
     ('grrr', 4),
     ('pain', 4),
     ('pfft', 4),
     ('sigh', 4),
     ('shes', 4),
     ('ROOM', 4),
     (',,,,', 4),
     ('lord', 4),
     ('mmmm', 4),
     ('ones', 4),
     ('huge', 4),
     ('woot', 4),
     ('shot', 4),
     ('team', 4),
     ('ways', 4),
     ('beat', 4),
     ('kent', 4),
     ('U130', 4),
     ('U196', 4),
     ('U219', 4),
     ('turn', 4),
     ('lame', 4),
     ('U123', 4),
     ('U154', 4),
     ('U988', 4),
     ('puff', 4),
     ('U146', 4),
     ('U989', 4),
     ('U117', 4),
     ('U819', 4),
     ('U820', 4),
     ('clap', 3),
     ('itch', 3),
     ('guyz', 3),
     ('U136', 3),
     ('gold', 3),
     ('ring', 3),
     ('isnt', 3),
     ('U141', 3),
     ('Only', 3),
     ('U148', 3),
     ('Your', 3),
     ('deal', 3),
     ('wash', 3),
     ('U109', 3),
     ('piff', 3),
     ('jump', 3),
     ('band', 3),
     ('orgy', 3),
     ('slap', 3),
     ('soft', 3),
     ('bend', 3),
     ('toss', 3),
     ('amen', 3),
     ('rain', 3),
     ('deop', 3),
     ('roof', 3),
     ('((((', 3),
     ('CHAT', 3),
     ('ahem', 3),
     ('hola', 3),
     ('butt', 3),
     ('imma', 3),
     ('town', 3),
     ('hawt', 3),
     ('2006', 3),
     ('Elev', 3),
     ('Wind', 3),
     ('AKDT', 3),
     ('lead', 3),
     ('DING', 3),
     ('note', 3),
     ('gawd', 3),
     ('half', 3),
     ('mary', 3),
     ('ello', 3),
     ('hick', 3),
     ('wine', 3),
     ('hiii', 3),
     ('bare', 3),
     ('vote', 3),
     ('Same', 3),
     ('wack', 3),
     ('snow', 3),
     ('hurt', 3),
     ('move', 3),
     ('road', 3),
     ('walk', 3),
     ('yawn', 3),
     ('hail', 3),
     ('nana', 3),
     ('U106', 3),
     ('hump', 3),
     ('elle', 3),
     ('yada', 3),
     ('tune', 3),
     ('hank', 3),
     ('slow', 3),
     ('rubs', 3),
     ('skin', 3),
     ('died', 3),
     ('U145', 3),
     ('swim', 3),
     ('U163', 3),
     ('army', 3),
     ('THAT', 3),
     ('wazz', 3),
     ('toes', 3),
     ('U153', 3),
     ('golf', 2),
     ('drew', 2),
     ('cast', 2),
     ('Days', 2),
     ('opps', 2),
     ('U138', 2),
     ('plan', 2),
     ('Just', 2),
     ('deaf', 2),
     ('deep', 2),
     ('phil', 2),
     ('hmph', 2),
     ('U155', 2),
     ('Poor', 2),
     ('Lies', 2),
     ('bite', 2),
     ('mins', 2),
     ('eats', 2),
     ('>:->', 2),
     ('cell', 2),
     ('cmon', 2),
     ('wats', 2),
     ('kind', 2),
     ('mike', 2),
     ('whoa', 2),
     ('dumb', 2),
     ('park', 2),
     ('Sure', 2),
     ('Come', 2),
     ('O.k.', 2),
     ('mama', 2),
     ('Nice', 2),
     ('hold', 2),
     ('ohio', 2),
     ('whip', 2),
     ('twin', 2),
     ('burp', 2),
     ('blew', 2),
     ('temp', 2),
     ('corn', 2),
     ('pool', 2),
     ('cash', 2),
     ('ears', 2),
     ('From', 2),
     ('porn', 2),
     ('heal', 2),
     ('Dang', 2),
     ('ciao', 2),
     ('DOES', 2),
     ('typo', 2),
     ('Stop', 2),
     ('eric', 2),
     ('Drew', 2),
     ('sore', 2),
     ('Live', 2),
     ('High', 2),
     ('hits', 2),
     ('KoOL', 2),
     ('past', 2),
     ('Love', 2),
     ('meat', 2),
     ('!!!.', 2),
     ('argh', 2),
     ('limp', 2),
     ('rent', 2),
     ('cars', 2),
     ('Tell', 2),
     ('shop', 2),
     ('U172', 2),
     ('five', 2),
     ('sell', 2),
     ('<<<<', 2),
     ('city', 2),
     ('yard', 2),
     ('grrl', 2),
     ('chip', 2),
     ('bear', 2),
     ('foot', 2),
     ('uses', 2),
     ('DONT', 2),
     ('sort', 2),
     ('lies', 2),
     ('whud', 2),
     ('hott', 2),
     ('Down', 2),
     ('Lets', 2),
     ('club', 2),
     ('adds', 2),
     ('Here', 2),
     ('born', 2),
     ('wOOt', 2),
     ('area', 2),
     ('?!?!', 2),
     ('Ohio', 2),
     ('U112', 2),
     ('humm', 2),
     ('newp', 2),
     ('gays', 2),
     ('zone', 2),
     ('hint', 2),
     ('spin', 2),
     ('ewww', 2),
     ('pies', 2),
     ('doll', 2),
     ('drop', 2),
     ('gimp', 2),
     ('spot', 2),
     ('ages', 2),
     ('clue', 2),
     ('mass', 2),
     ('Ummm', 2),
     ('Gosh', 2),
     ('flow', 2),
     ('kewl', 2),
     ('hall', 2),
     ('haze', 2),
     ('1996', 2),
     ('John', 2),
     ('john', 2),
     ('sooo', 2),
     ('cost', 2),
     ('trip', 2),
     ('babi', 2),
     ('rich', 2),
     ('U100', 2),
     ('n9ne', 2),
     ('Ahhh', 2),
     ('??!!', 2),
     ('U111', 2),
     ('moon', 2),
     ('STOP', 2),
     ('any1', 2),
     ('yeas', 2),
     ('wooo', 2),
     ('<333', 2),
     ('tick', 2),
     ('tock', 2),
     ('WITH', 2),
     ('FROM', 2),
     ('side', 2),
     ('Heyy', 2),
     ('howz', 2),
     ("ex's", 2),
     ('Cool', 2),
     ('U170', 2),
     ('U175', 2),
     ('root', 2),
     ('tyvm', 2),
     ('luvs', 2),
     ('fits', 2),
     ('rofl', 2),
     ('sand', 2),
     ('ltns', 2),
     ('flaw', 2),
     ('aunt', 2),
     ('lawl', 2),
     ('Okay', 2),
     ('HAVE', 2),
     ('NONE', 2),
     ('YOUR', 2),
     ('Lmao', 2),
     ('Tisk', 2),
     ('U190', 2),
     ('tisk', 2),
     ('draw', 1),
     ('docs', 1),
     ('Slip', 1),
     ('Fade', 1),
     ('bowl', 1),
     ('bong', 1),
     ('ogan', 1),
     ('cams', 1),
     ('gooo', 1),
     ('yeee', 1),
     ('ahah', 1),
     ('jeep', 1),
     ('Deep', 1),
     ('Show', 1),
     ('Turn', 1),
     ('Hand', 1),
     ('VBox', 1),
     ('ELSE', 1),
     ('serg', 1),
     ('bein', 1),
     ('whys', 1),
     ('tape', 1),
     ('sexs', 1),
     ('form', 1),
     ('HUGE', 1),
     ('nads', 1),
     ('owww', 1),
     ('gags', 1),
     ('Meep', 1),
     ('LAst', 1),
     ("pm's", 1),
     ('1.99', 1),
     ('lool', 1),
     ('kina', 1),
     ('sext', 1),
     ('lazy', 1),
     ('calm', 1),
     ('arms', 1),
     ('smax', 1),
     ('VVil', 1),
     ('este', 1),
     ('chik', 1),
     ('Boyz', 1),
     ('coat', 1),
     ('Eyes', 1),
     ('Dawn', 1),
     ('LIVE', 1),
     ('mauh', 1),
     ('ques', 1),
     ('4.20', 1),
     ('gosh', 1),
     ('ruff', 1),
     ('mame', 1),
     ('nada', 1),
     ('push', 1),
     ('prob', 1),
     ('wild', 1),
     ('whew', 1),
     ('dark', 1),
     ('waht', 1),
     ('test', 1),
     ('boot', 1),
     ('hiom', 1),
     ('HAHA', 1),
     ('dman', 1),
     ('jail', 1),
     ('cops', 1),
     ('hogs', 1),
     ('peek', 1),
     ('MORE', 1),
     ('TIME', 1),
     ('loud', 1),
     ('o.k.', 1),
     ('Sexy', 1),
     ('Ctrl', 1),
     ('hots', 1),
     ('Need', 1),
     ('frst', 1),
     ('1200', 1),
     ('crop', 1),
     ('bomb', 1),
     ('Pour', 1),
     ('pour', 1),
     ('Swim', 1),
     ('Hard', 1),
     ('eeek', 1),
     ('tjhe', 1),
     ('10th', 1),
     ('heee', 1),
     ('peel', 1),
     ('fock', 1),
     ('Kold', 1),
     ('exit', 1),
     ('kold', 1),
     ('3:45', 1),
     ('MRIs', 1),
     ('buff', 1),
     ('plus', 1),
     ('tory', 1),
     ('knee', 1),
     ('OOPS', 1),
     ('oooh', 1),
     ('lala', 1),
     ('fake', 1),
     ('ssid', 1),
     ('poot', 1),
     ('poop', 1),
     ('bird', 1),
     ('plow', 1),
     ('thnx', 1),
     ('card', 1),
     ('Hugs', 1),
     ('Lord', 1),
     ('uyes', 1),
     ('benz', 1),
     ('<~~~', 1),
     ('disc', 1),
     ('LONG', 1),
     ('Been', 1),
     ('Will', 1),
     ('bloe', 1),
     ('blow', 1),
     ('hooo', 1),
     ('thje', 1),
     ('Jess', 1),
     ('term', 1),
     ('Tina', 1),
     ('ooer', 1),
     ('HALO', 1),
     ('Awww', 1),
     ('anal', 1),
     ('Drop', 1),
     ('dojn', 1),
     ('wubs', 1),
     ('mkay', 1),
     ('spat', 1),
     ('gees', 1),
     ('hawT', 1),
     ('yes.', 1),
     ('puts', 1),
     ('fish', 1),
     ('size', 1),
     ('39.3', 1),
     ('1980', 1),
     ('64.8', 1),
     ('syck', 1),
     ('tere', 1),
     ('U542', 1),
     ('sent', 1),
     ('45.5', 1),
     ('98.5', 1),
     ('1299', 1),
     ('1900', 1),
     ('1930', 1),
     ('Werd', 1),
     ('Rofl', 1),
     ('mode', 1),
     ('nawt', 1),
     ('sign', 1),
     ('woof', 1),
     ('sum1', 1),
     ('ghet', 1),
     ('brad', 1),
     ('offa', 1),
     ('Dood', 1),
     ('out.', 1),
     ('LOUD', 1),
     ('sink', 1),
     ('FINE', 1),
     ('cums', 1),
     ('loss', 1),
     ('Life', 1),
     ('Damn', 1),
     ('wrap', 1),
     ('hide', 1),
     ("PM's", 1),
     ('Talk', 1),
     ('okey', 1),
     ('worl', 1),
     ('Hold', 1),
     ('cepn', 1),
     ('lots', 1),
     ('Mary', 1),
     ('nawp', 1),
     ('addy', 1),
     ('lake', 1),
     ('slip', 1),
     ('mite', 1),
     ('wood', 1),
     ('orta', 1),
     ('wins', 1),
     ('ebay', 1),
     ('coem', 1),
     ('giva', 1),
     ('1.98', 1),
     ('ally', 1),
     ('Judy', 1),
     ('cyas', 1),
     ('shup', 1),
     ('tooo', 1),
     ("pm'n", 1),
     ('choc', 1),
     ('wher', 1),
     ('whoo', 1),
     ('dint', 1),
     ('tend', 1),
     ('menu', 1),
     ('lust', 1),
     ('nods', 1),
     ('NAME', 1),
     ('kept', 1),
     ('scuk', 1),
     ('raed', 1),
     ('Then', 1),
     ('bugs', 1),
     ('nerd', 1),
     ('Hill', 1),
     ('Evil', 1),
     ('saME', 1),
     ('2Pac', 1),
     ('Time', 1),
     ('pimp', 1),
     ('haaa', 1),
     ('98.6', 1),
     ("it's", 1),
     ('Mono', 1),
     ('mono', 1),
     ('Bone', 1),
     ('Hero', 1),
     ('Came', 1),
     ('.op.', 1),
     ('Hott', 1),
     ('Joey', 1),
     ('Jane', 1),
     ('span', 1),
     ('wore', 1),
     ('QUIT', 1),
     ('pasa', 1),
     ('barn', 1),
     ('Kick', 1),
     ('feat', 1),
     ('Back', 1),
     ('dork', 1),
     ('laid', 1),
     ('Home', 1),
     ('herd', 1),
     ('Born', 1),
     ('Away', 1),
     ('Tide', 1),
     ('jush', 1),
     ('Cute', 1),
     ('GrlZ', 1),
     ('lung', 1),
     ('SOME', 1),
     ('Lion', 1),
     ('brat', 1),
     (':o *', 1),
     ('MUAH', 1),
     ('fawk', 1),
     ('dust', 1),
     ('Help', 1),
     ('seth', 1),
     ('Heya', 1),
     ('bone', 1),
     ('abou', 1),
     ('tthe', 1),
     ('Even', 1),
     ('herE', 1),
     ('Hail', 1),
     ('halo', 1),
     ('pork', 1),
     ('1cos', 1),
     ("yw's", 1),
     ('mark', 1),
     ('dotn', 1),
     ('PMSL', 1),
     ('pmsl', 1),
     ('gift', 1),
     ('outs', 1),
     ('Paul', 1),
     ('outa', 1),
     ('York', 1),
     ('Care', 1),
     ('Chat', 1),
     ('fear', 1),
     ('dies', 1),
     ('givs', 1),
     ('bust', 1),
     ('xmas', 1),
     ('enuf', 1),
     ('LoVe', 1),
     ('eeww', 1),
     ('dick', 1),
     ('fair', 1),
     ('lyin', 1),
     ('lois', 1),
     ('cuss', 1),
     ('LATE', 1),
     ('THEY', 1),
     ('GOOD', 1),
     ('rape', 1),
     ('geez', 1),
     ('tart', 1),
     ('hgey', 1),
     ('caan', 1),
     ('lol.', 1),
     ('Elle', 1),
     ('nude', 1),
     ('allo', 1),
     ('yesh', 1),
     ('wind', 1),
     ('Reub', 1),
     ('!???', 1),
     ('heat', 1),
     ('kmph', 1),
     ('pope', 1),
     ('yess', 1),
     ('!...', 1),
     ('duet', 1),
     ('wuts', 1),
     ('west', 1),
     ('quiz', 1),
     ('scar', 1),
     ('Girl', 1),
     ('pair', 1),
     ('Rang', 1),
     ('rang', 1),
     ('bell', 1),
     ('dawg', 1),
     ('febe', 1),
     ('Prof', 1),
     ('Kewl', 1),
     ('jude', 1),
     ('Yoko', 1),
     ('seee', 1),
     ('whou', 1),
     ('idnt', 1),
     ('perk', 1),
     ('http', 1),
     ('2DAY', 1),
     ('yell', 1),
     ('mang', 1),
     ('SSRI', 1),
     ('cure', 1),
     ('wean', 1),
     ('post', 1),
     ('anti', 1),
     ('noth', 1),
     ('tall', 1),
     ('pray', 1),
     ('weed', 1),
     ('icky', 1),
     ('Rick', 1),
     ('spit', 1),
     ('lube', 1),
     ('mami', 1),
     ('east', 1),
     ('18ST', 1),
     ('seat', 1),
     ('cock', 1),
     ('SExy', 1),
     ('otay', 1),
     ('firs', 1),
     ('site', 1),
     ('U113', 1),
     ('dump', 1),
     ('toop', 1),
     ('four', 1),
     ('U118', 1),
     ('sets', 1),
     ('asss', 1),
     ('paid', 1),
     ('Iowa', 1),
     ('Teck', 1),
     ('"...', 1),
     ('jeff', 1),
     ('crib', 1),
     ('drug', 1),
     ('cook', 1),
     ('9:10', 1),
     ('ladz', 1),
     ('aime', 1),
     ('hong', 1),
     ('kong', 1),
     ('Oops', 1),
     ('tits', 1),
     ('gret', 1),
     ('guns', 1),
     ('inch', 1),
     ('sean', 1),
     ('howl', 1),
     ('Take', 1),
     ('z-ro', 1),
     ('U137', 1),
     ('Haha', 1),
     ('1985', 1),
     ('slam', 1),
     ('pine', 1),
     ('puke', 1),
     ('waaa', 1),
     ('urls', 1),
     ('star', 1),
     ('Save', 1),
     ('teck', 1),
     ('Room', 1),
     ('sori', 1),
     ('Long', 1),
     ('poem', 1),
     ...]




```python
f = FreqDist(text1)
f = FreqDist([len(w) for w in text1]) #frequency distribution of lengths of words
f = FreqDist([w.upper() for w in text1]) #frequency distribution of words which are in uppercase
f
```




    FreqDist({',': 18713, 'THE': 14431, '.': 6862, 'OF': 6609, 'AND': 6430, 'A': 4736, 'TO': 4625, 'IN': 4172, ';': 4072, 'THAT': 3085, ...})



In list comprehension you can (1) filter and (2) map something in the list to something else using a function. List comprehension expressions are really important. Lets see what we can do with Fequency distributions in NLTK. 

FreqDist is a set of pairs (dictionary) where the first item is a key and the secons item is a value. 


```python
f = FreqDist(sent1)
f['me']
# here we changed frequency of how often "me" happens, if we create FerqDist by ourselves, this can be important
f['me'] += 1
# here we are adding a new word "you"
f['you'] += 1 
```


```python
f.plot
```




    <bound method FreqDist.plot of FreqDist({'me': 2, 'Call': 1, 'Ishmael': 1, '.': 1, 'you': 1})>




```python
[w for w in sent7 if len(w) == 4]
```




    ['will', 'join', 'Nov.']




```python
"en" in "banen"
```




    True




```python
"en" in "banned"
```




    False




```python
sorted(w for w in set(text7) if '-' in w and 'index' in w)
```




    ['Stock-index',
     'index-arbitrage',
     'index-fund',
     'index-options',
     'index-related',
     'stock-index']




```python
sorted(wd for wd in set(text3) if wd.istitle() and len(wd) > 10)
```




    ['Abelmizraim',
     'Allonbachuth',
     'Beerlahairoi',
     'Canaanitish',
     'Chedorlaomer',
     'Girgashites',
     'Hazarmaveth',
     'Hazezontamar',
     'Ishmeelites',
     'Jegarsahadutha',
     'Jehovahjireh',
     'Kirjatharba',
     'Melchizedek',
     'Mesopotamia',
     'Peradventure',
     'Philistines',
     'Zaphnathpaaneah']




```python
sorted(w for w in set(sent7) if not w.islower())
```




    [',', '.', '29', '61', 'Nov.', 'Pierre', 'Vinken']




```python
word = "cat"
if len(word) < 5:
    print("blablabla")
```

    blablabla



```python
#Loops: for ... there are similar with list cmprehension, but we do not create a lisyt here, btu executing some code
```


```python
for w in sent1:
    print(w, len(w))
```

    Call 4
    me 2
    Ishmael 7
    . 1



```python
#putting things into each other
for w in sent1:
    if w.endswith("l"):
        print(w)
```

    Call
    Ishmael



```python

```


```python
#21. What is the difference between the following two tests: w.isupper() and not w.islower()?
w = "Ring"
w.isupper() 
#gets True when all characters are uppecase, 
#all other situations - False
```




    False




```python
w = "Ring"
not w.islower()
#gets False only when all characters are lower case
#all other situations - True
```




    True




```python
#22. Write the slice expression that extracts the last two words of text2.
text2[-2:]
```




    ['THE', 'END']




```python
#23. Review the discussion of looping with conditions in 4. 
# Use a combination of for and if statements to loop over the words of the movie script for 
# Monty Python and the Holy Grail (text6) and print all the uppercase words, one per line.

for word in text6:
    if word.isupper():
        print(word)
```

    SCENE
    KING
    ARTHUR
    SOLDIER
    ARTHUR
    I
    SOLDIER
    ARTHUR
    I
    I
    SOLDIER
    ARTHUR
    SOLDIER
    ARTHUR
    SOLDIER
    ARTHUR
    SOLDIER
    ARTHUR
    SOLDIER
    ARTHUR
    SOLDIER
    ARTHUR
    SOLDIER
    ARTHUR
    SOLDIER
    A
    ARTHUR
    SOLDIER
    A
    ARTHUR
    SOLDIER
    ARTHUR
    SOLDIER
    I
    ARTHUR
    I
    SOLDIER
    SOLDIER
    SOLDIER
    I
    ARTHUR
    SOLDIER
    SOLDIER
    SOLDIER
    SOLDIER
    SOLDIER
    SOLDIER
    SOLDIER
    SOLDIER
    SCENE
    CART
    MASTER
    CUSTOMER
    CART
    MASTER
    DEAD
    PERSON
    I
    CART
    MASTER
    CUSTOMER
    DEAD
    PERSON
    I
    CART
    MASTER
    CUSTOMER
    DEAD
    PERSON
    I
    CART
    MASTER
    CUSTOMER
    DEAD
    PERSON
    I
    CUSTOMER
    CART
    MASTER
    I
    DEAD
    PERSON
    I
    CUSTOMER
    CART
    MASTER
    I
    DEAD
    PERSON
    I
    CUSTOMER
    CART
    MASTER
    I
    CUSTOMER
    CART
    MASTER
    I
    CUSTOMER
    CART
    MASTER
    DEAD
    PERSON
    I
    I
    CUSTOMER
    DEAD
    PERSON
    I
    I
    CUSTOMER
    CART
    MASTER
    CUSTOMER
    CART
    MASTER
    I
    CUSTOMER
    CART
    MASTER
    SCENE
    ARTHUR
    DENNIS
    ARTHUR
    DENNIS
    I
    ARTHUR
    I
    DENNIS
    I
    I
    ARTHUR
    I
    DENNIS
    ARTHUR
    I
    DENNIS
    ARTHUR
    I
    DENNIS
    I
    ARTHUR
    I
    DENNIS
    WOMAN
    ARTHUR
    I
    WOMAN
    ARTHUR
    WOMAN
    ARTHUR
    I
    WOMAN
    I
    I
    DENNIS
    A
    WOMAN
    DENNIS
    ARTHUR
    I
    WOMAN
    ARTHUR
    WOMAN
    ARTHUR
    DENNIS
    I
    ARTHUR
    DENNIS
    ARTHUR
    I
    DENNIS
    ARTHUR
    DENNIS
    ARTHUR
    I
    WOMAN
    ARTHUR
    I
    WOMAN
    I
    ARTHUR
    WOMAN
    ARTHUR
    I
    I
    DENNIS
    ARTHUR
    DENNIS
    ARTHUR
    DENNIS
    I
    I
    I
    ARTHUR
    DENNIS
    ARTHUR
    DENNIS
    I
    ARTHUR
    DENNIS
    I
    SCENE
    BLACK
    KNIGHT
    BLACK
    KNIGHT
    GREEN
    KNIGHT
    BLACK
    KNIGHT
    GREEN
    KNIGHT
    BLACK
    KNIGHT
    BLACK
    KNIGHT
    GREEN
    KNIGHT
    GREEN
    KNIGHT
    BLACK
    KNIGHT
    GREEN
    KNIGHT
    BLACK
    KNIGHT
    ARTHUR
    I
    I
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    I
    I
    BLACK
    KNIGHT
    ARTHUR
    I
    BLACK
    KNIGHT
    I
    ARTHUR
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    A
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    I
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    I
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    I
    ARTHUR
    BLACK
    KNIGHT
    BLACK
    KNIGHT
    I
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    I
    ARTHUR
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    BLACK
    KNIGHT
    ARTHUR
    BLACK
    KNIGHT
    I
    I
    SCENE
    MONKS
    CROWD
    A
    A
    A
    A
    MONKS
    CROWD
    A
    A
    A
    A
    A
    A
    A
    A
    A
    A
    A
    A
    A
    VILLAGER
    CROWD
    BEDEVERE
    VILLAGER
    CROWD
    BEDEVERE
    WITCH
    I
    I
    BEDEVERE
    WITCH
    CROWD
    WITCH
    BEDEVERE
    VILLAGER
    BEDEVERE
    VILLAGER
    VILLAGER
    CROWD
    BEDEVERE
    VILLAGER
    VILLAGER
    VILLAGER
    VILLAGER
    VILLAGERS
    VILLAGER
    VILLAGER
    VILLAGER
    VILLAGER
    A
    VILLAGERS
    A
    VILLAGER
    A
    VILLAGER
    RANDOM
    BEDEVERE
    VILLAGER
    BEDEVERE
    A
    VILLAGER
    I
    VILLAGER
    VILLAGER
    CROWD
    BEDEVERE
    VILLAGER
    VILLAGER
    VILLAGER
    CROWD
    BEDEVERE
    VILLAGER
    VILLAGER
    CROWD
    BEDEVERE
    VILLAGER
    VILLAGER
    VILLAGER
    BEDEVERE
    VILLAGER
    B
    BEDEVERE
    CROWD
    BEDEVERE
    VILLAGER
    BEDEVERE
    VILLAGER
    RANDOM
    BEDEVERE
    VILLAGER
    VILLAGER
    VILLAGER
    CROWD
    BEDEVERE
    VILLAGER
    VILLAGER
    VILLAGER
    VILLAGER
    VILLAGER
    VILLAGER
    VILLAGER
    VILLAGER
    VILLAGER
    ARTHUR
    A
    CROWD
    BEDEVERE
    VILLAGER
    BEDEVERE
    VILLAGER
    A
    VILLAGER
    A
    CROWD
    A
    A
    VILLAGER
    BEDEVERE
    CROWD
    BEDEVERE
    CROWD
    A
    A
    A
    WITCH
    VILLAGER
    CROWD
    BEDEVERE
    ARTHUR
    I
    BEDEVERE
    ARTHUR
    BEDEVERE
    I
    ARTHUR
    BEDEVERE
    ARTHUR
    I
    NARRATOR
    SCENE
    SIR
    BEDEVERE
    ARTHUR
    BEDEVERE
    SIR
    LAUNCELOT
    ARTHUR
    SIR
    GALAHAD
    LAUNCELOT
    PATSY
    ARTHUR
    I
    KNIGHTS
    PRISONER
    KNIGHTS
    MAN
    I
    ARTHUR
    KNIGHTS
    SCENE
    GOD
    I
    ARTHUR
    GOD
    I
    I
    ARTHUR
    I
    O
    GOD
    ARTHUR
    GOD
    ARTHUR
    O
    GOD
    LAUNCELOT
    A
    A
    GALAHAD
    SCENE
    ARTHUR
    FRENCH
    GUARD
    ARTHUR
    FRENCH
    GUARD
    ARTHUR
    FRENCH
    GUARD
    I
    I
    ARTHUR
    GALAHAD
    ARTHUR
    FRENCH
    GUARD
    I
    ARTHUR
    FRENCH
    GUARD
    ARTHUR
    FRENCH
    GUARD
    I
    I
    GALAHAD
    FRENCH
    GUARD
    ARTHUR
    FRENCH
    GUARD
    I
    GALAHAD
    ARTHUR
    FRENCH
    GUARD
    I
    I
    GALAHAD
    FRENCH
    GUARD
    I
    ARTHUR
    I
    FRENCH
    GUARD
    OTHER
    FRENCH
    GUARD
    FRENCH
    GUARD
    ARTHUR
    I
    KNIGHTS
    ARTHUR
    KNIGHTS
    FRENCH
    GUARD
    FRENCH
    GUARD
    ARTHUR
    KNIGHTS
    FRENCH
    GUARD
    FRENCH
    GUARDS
    LAUNCELOT
    I
    ARTHUR
    BEDEVERE
    I
    FRENCH
    GUARDS
    C
    A
    ARTHUR
    BEDEVERE
    I
    ARTHUR
    BEDEVERE
    U
    I
    ARTHUR
    BEDEVERE
    ARTHUR
    KNIGHTS
    CRASH
    FRENCH
    GUARDS
    SCENE
    VOICE
    DIRECTOR
    HISTORIAN
    KNIGHT
    KNIGHT
    HISTORIAN
    HISTORIAN
    S
    WIFE
    SCENE
    NARRATOR
    MINSTREL
    O
    SIR
    ROBIN
    DENNIS
    WOMAN
    ALL
    HEADS
    MINSTREL
    ROBIN
    I
    ALL
    HEADS
    MINSTREL
    ROBIN
    I
    ALL
    HEADS
    I
    ROBIN
    W
    I
    I
    ALL
    HEADS
    ROBIN
    I
    LEFT
    HEAD
    I
    MIDDLE
    HEAD
    I
    RIGHT
    HEAD
    I
    MIDDLE
    HEAD
    I
    LEFT
    HEAD
    I
    RIGHT
    HEAD
    LEFT
    HEAD
    ROBIN
    I
    LEFT
    HEAD
    I
    RIGHT
    HEAD
    MIDDLE
    HEAD
    LEFT
    HEAD
    RIGHT
    HEAD
    MIDDLE
    HEAD
    LEFT
    HEAD
    MIDDLE
    HEAD
    LEFT
    HEAD
    I
    MIDDLE
    HEAD
    RIGHT
    HEAD
    LEFT
    HEAD
    MIDDLE
    HEAD
    RIGHT
    HEAD
    LEFT
    HEAD
    ALL
    HEADS
    MIDDLE
    HEAD
    RIGHT
    HEAD
    MINSTREL
    ROBIN
    MINSTREL
    ROBIN
    I
    MINSTREL
    ROBIN
    MINSTREL
    ROBIN
    I
    MINSTREL
    ROBIN
    I
    MINSTREL
    ROBIN
    MINSTREL
    ROBIN
    I
    CARTOON
    MONKS
    CARTOON
    CHARACTER
    CARTOON
    MONKS
    CARTOON
    CHARACTERS
    CARTOON
    MONKS
    CARTOON
    CHARACTER
    VOICE
    CARTOON
    CHARACTER
    SCENE
    NARRATOR
    GALAHAD
    GIRLS
    ZOOT
    GALAHAD
    ZOOT
    GALAHAD
    ZOOT
    GALAHAD
    ZOOT
    MIDGET
    CRAPPER
    O
    ZOOT
    MIDGET
    CRAPPER
    ZOOT
    GALAHAD
    I
    I
    ZOOT
    GALAHAD
    ZOOT
    GALAHAD
    ZOOT
    GALAHAD
    I
    ZOOT
    GALAHAD
    I
    I
    ZOOT
    I
    GALAHAD
    ZOOT
    PIGLET
    GALAHAD
    ZOOT
    GALAHAD
    B
    ZOOT
    WINSTON
    GALAHAD
    PIGLET
    GALAHAD
    PIGLET
    GALAHAD
    I
    PIGLET
    GALAHAD
    I
    PIGLET
    GALAHAD
    I
    I
    I
    GIRLS
    GALAHAD
    GIRLS
    GALAHAD
    DINGO
    I
    GALAHAD
    I
    DINGO
    GALAHAD
    I
    I
    DINGO
    GALAHAD
    DINGO
    I
    GALAHAD
    DINGO
    I
    LEFT
    HEAD
    DENNIS
    OLD
    MAN
    TIM
    THE
    ENCHANTER
    ARMY
    OF
    KNIGHTS
    DINGO
    I
    GOD
    DINGO
    GIRLS
    A
    A
    DINGO
    AMAZING
    STUNNER
    LOVELY
    DINGO
    GIRLS
    A
    A
    DINGO
    GIRLS
    GALAHAD
    I
    LAUNCELOT
    GALAHAD
    LAUNCELOT
    GALAHAD
    LAUNCELOT
    GALAHAD
    LAUNCELOT
    DINGO
    LAUNCELOT
    GALAHAD
    LAUNCELOT
    GALAHAD
    I
    LAUNCELOT
    GIRLS
    GALAHAD
    I
    DINGO
    GIRLS
    LAUNCELOT
    GALAHAD
    I
    I
    DINGO
    GIRLS
    LAUNCELOT
    GALAHAD
    I
    DINGO
    GIRLS
    DINGO
    LAUNCELOT
    GALAHAD
    I
    I
    LAUNCELOT
    GALAHAD
    LAUNCELOT
    GALAHAD
    I
    LAUNCELOT
    GALAHAD
    LAUNCELOT
    GALAHAD
    I
    LAUNCELOT
    I
    NARRATOR
    I
    I
    CROWD
    NARRATOR
    I
    SCENE
    OLD
    MAN
    ARTHUR
    OLD
    MAN
    ARTHUR
    OLD
    MAN
    ARTHUR
    OLD
    MAN
    ARTHUR
    OLD
    MAN
    ARTHUR
    OLD
    MAN
    ARTHUR
    OLD
    MAN
    SCENE
    HEAD
    KNIGHT
    OF
    NI
    KNIGHTS
    OF
    NI
    ARTHUR
    HEAD
    KNIGHT
    RANDOM
    ARTHUR
    HEAD
    KNIGHT
    BEDEVERE
    HEAD
    KNIGHT
    RANDOM
    ARTHUR
    HEAD
    KNIGHT
    ARTHUR
    HEAD
    KNIGHT
    KNIGHTS
    OF
    NI
    ARTHUR
    HEAD
    KNIGHT
    ARTHUR
    HEAD
    KNIGHT
    ARTHUR
    A
    KNIGHTS
    OF
    NI
    ARTHUR
    PARTY
    ARTHUR
    HEAD
    KNIGHT
    ARTHUR
    O
    HEAD
    KNIGHT
    ARTHUR
    HEAD
    KNIGHT
    ARTHUR
    HEAD
    KNIGHT
    CARTOON
    CHARACTER
    SUN
    CARTOON
    CHARACTER
    SUN
    CARTOON
    CHARACTER
    SUN
    CARTOON
    CHARACTER
    SCENE
    NARRATOR
    FATHER
    PRINCE
    HERBERT
    FATHER
    HERBERT
    FATHER
    HERBERT
    B
    I
    FATHER
    I
    I
    I
    I
    I
    I
    HERBERT
    I
    I
    FATHER
    HERBERT
    I
    FATHER
    I
    HERBERT
    B
    I
    FATHER
    HERBERT
    FATHER
    HERBERT
    I
    FATHER
    HERBERT
    I
    I
    I
    FATHER
    I
    GUARD
    GUARD
    FATHER
    I
    GUARD
    FATHER
    GUARD
    GUARD
    FATHER
    GUARD
    FATHER
    GUARD
    FATHER
    GUARD
    GUARD
    FATHER
    GUARD
    FATHER
    GUARD
    FATHER
    GUARD
    FATHER
    GUARD
    FATHER
    GUARD
    I
    FATHER
    N
    GUARD
    FATHER
    GUARD
    FATHER
    GUARD
    GUARD
    FATHER
    GUARD
    FATHER
    GUARD
    GUARD
    FATHER
    GUARD
    FATHER
    GUARD
    FATHER
    GUARD
    GUARD
    GUARD
    I
    FATHER
    GUARD
    GUARD
    FATHER
    GUARD
    FATHER
    I
    GUARD
    I
    HERBERT
    FATHER
    GUARD
    FATHER
    SCENE
    LAUNCELOT
    CONCORDE
    LAUNCELOT
    CONCORDE
    LAUNCELOT
    I
    I
    A
    A
    CONCORDE
    I
    I
    LAUNCELOT
    CONCORDE
    I
    I
    I
    I
    I
    LAUNCELOT
    I
    CONCORDE
    I
    I
    LAUNCELOT
    I
    I
    CONCORDE
    LAUNCELOT
    CONCORDE
    I
    LAUNCELOT
    CONCORDE
    I
    I
    I
    SCENE
    PRINCESS
    LUCKY
    GIRLS
    GUEST
    SENTRY
    SENTRY
    SENTRY
    LAUNCELOT
    SENTRY
    LAUNCELOT
    PRINCESS
    LUCKY
    GIRLS
    LAUNCELOT
    GUESTS
    LAUNCELOT
    GUARD
    LAUNCELOT
    O
    I
    I
    HERBERT
    LAUNCELOT
    I
    I
    HERBERT
    LAUNCELOT
    I
    HERBERT
    I
    I
    LAUNCELOT
    I
    HERBERT
    FATHER
    HERBERT
    I
    FATHER
    LAUNCELOT
    I
    HERBERT
    LAUNCELOT
    FATHER
    LAUNCELOT
    FATHER
    LAUNCELOT
    I
    I
    HERBERT
    I
    FATHER
    LAUNCELOT
    I
    FATHER
    I
    HERBERT
    FATHER
    LAUNCELOT
    I
    FATHER
    LAUNCELOT
    FATHER
    LAUNCELOT
    I
    I
    I
    FATHER
    HERBERT
    LAUNCELOT
    I
    FATHER
    LAUNCELOT
    HERBERT
    I
    FATHER
    LAUNCELOT
    HERBERT
    I
    LAUNCELOT
    I
    HERBERT
    LAUNCELOT
    I
    I
    I
    FATHER
    HERBERT
    SCENE
    GUESTS
    FATHER
    GUEST
    FATHER
    LAUNCELOT
    FATHER
    LAUNCELOT
    I
    I
    I
    GUEST
    GUESTS
    FATHER
    LAUNCELOT
    GUEST
    GUESTS
    FATHER
    GUESTS
    FATHER
    I
    I
    GUEST
    FATHER
    GUEST
    FATHER
    BRIDE
    S
    FATHER
    GUEST
    FATHER
    I
    I
    LAUNCELOT
    GUEST
    GUESTS
    CONCORDE
    HERBERT
    I
    FATHER
    HERBERT
    I
    FATHER
    HERBERT
    I
    FATHER
    GUESTS
    FATHER
    GUESTS
    FATHER
    GUESTS
    FATHER
    GUESTS
    FATHER
    GUESTS
    CONCORDE
    GUESTS
    CONCORDE
    GUESTS
    LAUNCELOT
    GUESTS
    LAUNCELOT
    I
    GUESTS
    CONCORDE
    LAUNCELOT
    GUESTS
    LAUNCELOT
    GUESTS
    LAUNCELOT
    SCENE
    ARTHUR
    OLD
    CRONE
    ARTHUR
    CRONE
    ARTHUR
    I
    CRONE
    ARTHUR
    CRONE
    ARTHUR
    CRONE
    BEDEVERE
    ARTHUR
    BEDEVERE
    ARTHUR
    BEDEVERE
    ARTHUR
    BEDEVERE
    ARTHUR
    BEDEVERE
    ARTHUR
    ARTHUR
    BEDEVERE
    CRONE
    BEDEVERE
    ARTHUR
    CRONE
    BEDEVERE
    ARTHUR
    BEDEVERE
    ARTHUR
    BEDEVERE
    ROGER
    THE
    SHRUBBER
    ARTHUR
    ROGER
    ARTHUR
    ROGER
    I
    I
    BEDEVERE
    ARTHUR
    SCENE
    ARTHUR
    O
    HEAD
    KNIGHT
    I
    ARTHUR
    HEAD
    KNIGHT
    KNIGHTS
    OF
    NI
    HEAD
    KNIGHT
    RANDOM
    HEAD
    KNIGHT
    ARTHUR
    O
    HEAD
    KNIGHT
    ARTHUR
    RANDOM
    HEAD
    KNIGHT
    KNIGHTS
    OF
    NI
    A
    A
    A
    HEAD
    KNIGHT
    ARTHUR
    HEAD
    KNIGHT
    ARTHUR
    KNIGHTS
    OF
    NI
    HEAD
    KNIGHT
    ARTHUR
    HEAD
    KNIGHT
    I
    ARTHUR
    KNIGHTS
    OF
    NI
    HEAD
    KNIGHT
    ARTHUR
    KNIGHTS
    OF
    NI
    HEAD
    KNIGHT
    KNIGHTS
    OF
    NI
    BEDEVERE
    MINSTREL
    ARTHUR
    ROBIN
    HEAD
    KNIGHT
    ARTHUR
    MINSTREL
    ROBIN
    HEAD
    KNIGHT
    KNIGHTS
    OF
    NI
    ROBIN
    I
    KNIGHTS
    OF
    NI
    ROBIN
    ARTHUR
    KNIGHTS
    OF
    NI
    HEAD
    KNIGHT
    ARTHUR
    KNIGHTS
    OF
    NI
    HEAD
    KNIGHT
    ARTHUR
    HEAD
    KNIGHT
    I
    I
    I
    KNIGHTS
    OF
    NI
    NARRATOR
    KNIGHTS
    NARRATOR
    MINSTREL
    NARRATOR
    KNIGHTS
    NARRATOR
    A
    CARTOON
    CHARACTER
    NARRATOR
    CARTOON
    CHARACTER
    NARRATOR
    CARTOON
    CHARACTER
    NARRATOR
    CARTOON
    CHARACTER
    NARRATOR
    CARTOON
    CHARACTER
    NARRATOR
    SCENE
    KNIGHTS
    ARTHUR
    TIM
    THE
    ENCHANTER
    I
    ARTHUR
    TIM
    ARTHUR
    TIM
    ARTHUR
    TIM
    I
    ARTHUR
    O
    TIM
    ROBIN
    ARTHUR
    KNIGHTS
    ARTHUR
    BEDEVERE
    GALAHAD
    ROBIN
    BEDEVERE
    ROBIN
    BEDEVERE
    ARTHUR
    GALAHAD
    ARTHUR
    I
    I
    TIM
    A
    ARTHUR
    A
    TIM
    A
    ARTHUR
    I
    ROBIN
    Y
    ARTHUR
    GALAHAD
    KNIGHTS
    TIM
    ROBIN
    ARTHUR
    ROBIN
    GALAHAD
    ARTHUR
    ROBIN
    KNIGHTS
    ARTHUR
    TIM
    I
    KNIGHTS
    TIM
    ARTHUR
    O
    TIM
    ARTHUR
    SCENE
    GALAHAD
    ARTHUR
    TIM
    ARTHUR
    GALAHAD
    ARTHUR
    W
    TIM
    ARTHUR
    TIM
    ARTHUR
    TIM
    ARTHUR
    TIM
    ARTHUR
    TIM
    ARTHUR
    TIM
    ARTHUR
    TIM
    ROBIN
    I
    I
    TIM
    GALAHAD
    TIM
    GALAHAD
    ROBIN
    TIM
    I
    ROBIN
    TIM
    ARTHUR
    BORS
    TIM
    BORS
    ARTHUR
    TIM
    I
    ROBIN
    I
    TIM
    I
    I
    ARTHUR
    TIM
    ARTHUR
    TIM
    KNIGHTS
    KNIGHTS
    ARTHUR
    KNIGHTS
    TIM
    ARTHUR
    LAUNCELOT
    GALAHAD
    ARTHUR
    GALAHAD
    ARTHUR
    ROBIN
    ARTHUR
    GALAHAD
    ARTHUR
    GALAHAD
    LAUNCELOT
    ARTHUR
    LAUNCELOT
    ARTHUR
    MONKS
    ARTHUR
    LAUNCELOT
    I
    ARTHUR
    BROTHER
    MAYNARD
    SECOND
    BROTHER
    O
    MAYNARD
    SECOND
    BROTHER
    MAYNARD
    KNIGHTS
    ARTHUR
    GALAHAD
    ARTHUR
    SCENE
    ARTHUR
    LAUNCELOT
    GALAHAD
    ARTHUR
    MAYNARD
    GALAHAD
    LAUNCELOT
    ARTHUR
    MAYNARD
    ARTHUR
    MAYNARD
    BEDEVERE
    MAYNARD
    LAUNCELOT
    MAYNARD
    ARTHUR
    MAYNARD
    GALAHAD
    ARTHUR
    MAYNARD
    LAUNCELOT
    ARTHUR
    BEDEVERE
    GALAHAD
    BEDEVERE
    I
    LAUNCELOT
    ARTHUR
    LAUNCELOT
    KNIGHTS
    BEDEVERE
    LAUNCELOT
    BEDEVERE
    N
    LAUNCELOT
    BEDEVERE
    I
    ARTHUR
    GALAHAD
    MAYNARD
    BROTHER
    MAYNARD
    BEDEVERE
    ARTHUR
    KNIGHTS
    BEDEVERE
    KNIGHTS
    NARRATOR
    ANIMATOR
    NARRATOR
    SCENE
    GALAHAD
    ARTHUR
    ROBIN
    ARTHUR
    BEDEVERE
    ARTHUR
    GALAHAD
    ARTHUR
    GALAHAD
    ARTHUR
    ROBIN
    ARTHUR
    ROBIN
    I
    GALAHAD
    ARTHUR
    ROBIN
    ARTHUR
    ROBIN
    I
    LAUNCELOT
    I
    I
    ARTHUR
    GALAHAD
    ARTHUR
    LAUNCELOT
    I
    ARTHUR
    BRIDGEKEEPER
    LAUNCELOT
    I
    BRIDGEKEEPER
    LAUNCELOT
    BRIDGEKEEPER
    LAUNCELOT
    BRIDGEKEEPER
    LAUNCELOT
    BRIDGEKEEPER
    LAUNCELOT
    ROBIN
    BRIDGEKEEPER
    ROBIN
    I
    BRIDGEKEEPER
    ROBIN
    BRIDGEKEEPER
    ROBIN
    BRIDGEKEEPER
    ROBIN
    I
    BRIDGEKEEPER
    GALAHAD
    BRIDGEKEEPER
    GALAHAD
    I
    BRIDGEKEEPER
    GALAHAD
    BRIDGEKEEPER
    ARTHUR
    BRIDGEKEEPER
    ARTHUR
    BRIDGEKEEPER
    ARTHUR
    BRIDGEKEEPER
    I
    I
    BEDEVERE
    ARTHUR
    SCENE
    ARTHUR
    BEDEVERE
    ARTHUR
    BEDEVERE
    ARTHUR
    FRENCH
    GUARD
    ARTHUR
    I
    FRENCH
    GUARD
    I
    I
    ARTHUR
    FRENCH
    GUARD
    I
    ARTHUR
    FRENCH
    GUARDS
    ARTHUR
    FRENCH
    GUARD
    ARTHUR
    FRENCH
    GUARD
    FRENCH
    GUARDS
    ARTHUR
    BEDEVERE
    ARTHUR
    FRENCH
    GUARDS
    ARTHUR
    FRENCH
    GUARDS
    ARTHUR
    FRENCH
    GUARDS
    ARTHUR
    ARMY
    OF
    KNIGHTS
    HISTORIAN
    S
    WIFE
    I
    INSPECTOR
    OFFICER
    HISTORIAN
    S
    WIFE
    OFFICER
    INSPECTOR
    OFFICER
    BEDEVERE
    INSPECTOR
    OFFICER
    INSPECTOR
    OFFICER
    OFFICER
    RANDOM
    RANDOM
    OFFICER
    OFFICER
    OFFICER
    OFFICER
    INSPECTOR
    OFFICER
    CAMERAMAN



```python
#24. Write expressions for finding all words in text6 that meet the conditions listed below. 
# The result should be in the form of a list of words: ['word1', 'word2', ...].
#Ending in ize
#Containing the letter z
#Containing te sequence of letters pt
#Having all lowercase letters except for an initial capital (i.e., titlecase)

[w for w in text6 if w.endswith("ize") and 'z' in w and 'pt' in w and w.istitle()]
```




    []




```python
#25. Define sent to be the list of words ['she', 'sells', 'sea', 'shells', 'by', 'the', 'sea', 'shore']. 
# Now write code to perform the following tasks:

text = ['she', 'sells', 'sea', 'shells', 'by', 'the', 'sea', 'shore']

for word in text:
    if word.startswith("sh"):
        print(word)
    elif len(word) > 4:
        print(word)
```

    she
    sells
    shells
    shore



```python
#26. What does the following Python code do?  sum(len(w) for w in text1) 
# Can you use it to work out the average word length of a text?

sum(len(w) for w in text1) 
# This expression adds up lengths of all words in text1

text1_new = set([w.lower() for w in text1])

sum(len(w) for w in text1_new)/len(text1_new)
```




    7.355754164006732




```python
#27. Define a function called vocab_size(text) that has a single parameter for the text, 
# and which returns the vocabulary size of the text.

def vocab_size(text):
    vocab = len(set([w.lower() for w in text]))
    return vocab

vocab_size(text1)
```




    17231




```python
#28. Define a function percent(word, text) that calculates how often a given word occurs in a text, 
# and expresses the result as a percentage.
def percent(word, text):
    f = FreqDist
    occ = FreqDist(word)
    vocab = len(set([w.lower() for w in text]))
    return occ/vocab
percent("man", text1)
    
    
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-74-cce0c20c0f63> in <module>
          5     vocab = len(set([w.lower() for w in text]))
          6     return occ/vocab
    ----> 7 percent("man", text1)
          8 
          9 


    <ipython-input-74-cce0c20c0f63> in percent(word, text)
          4     occ = FreqDist(word)
          5     vocab = len(set([w.lower() for w in text]))
    ----> 6     return occ/vocab
          7 percent("man", text1)
          8 


    TypeError: unsupported operand type(s) for /: 'FreqDist' and 'int'



```python

```
