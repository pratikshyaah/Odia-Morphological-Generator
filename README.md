# Odia-Morphological-Generator
#"model:" "OdiaMorphGen",
#"achnowledgment:" [
#    "/content/drive/MyDrive/morph_analyzer/Odiaverb.txt"
#]
#"result": [
#    [
#      {
#        "token": "ଖାଇଲା",
#       "analyses":[
#           {
#               "lemma": "ଖା"
#                "stem": "ଖାଇ "
#               "Tag": "POS=V|Num=P|Person=1|Tense=Past"
#           }
#       ],
#       "space": ' '
#       
#      }
#    ]
#]

#==================MORPHOLOGICAL GENERATOR==============#

import re
#path= r'[/content/drive/MyDrive/morph_analyzer/Odiaverb.txt]'
#text=docx2txt.process("Odiaverb.docx")
#print(text)
with open("/content/drive/MyDrive/morph_analyzer/Odiaverb.txt") as od:  #pathway to get the corpora
  odia=od.read().split("\n")  #split the corpora
  print(odia) #show the corpora
with open("/content/drive/MyDrive/morph_analyzer/OdiaPOS.txt") as od1:
  odia1=od.read().split("\n") #states that this is a closed file
  print(odia1)
  
  ! pip install nltk
  
import os
import nltk
import nltk.corpus

len(odia) #shows the length of the corpus

#preprocessing them by deleting the spaces and other 
word2=[]
for st1 in odia:
  word=st1.split(' ')   #deleting space    
  #print("The Odia verbs are: ", word) #printing the verbs from the space
  word1=word[0].split()
  while word1=='':
    word2=word1
  print("The odia verbs are: ", word1)  #the root words are selected
  
  #segmenting the tokens or lemma from the spaces
from nltk.corpus import wordnet as wn
#nltk.download(punkt)
from nltk.stem.wordnet import WordNetLemmatizer
! pip install word_tokenizer
! pip install pos_tag
from nltk import word_tokenize, pos_tag
from collections import defaultdict

tokens=word_tokenize(word)
lemma_function=WordNetLemmatizer()
for token,tag in pos_tag(tokens):
  lemma=lemma_function.lemmatize(token,tag_map[tag[0]])
  print(token, "=", lemma)
  
  word1=['ଖାଇ', 
'ଖେଳି',
'ଆସି',
'ଦେଖି',
'ଲେଖି', 
'ଚାଲି', 
'ଢାଳି', 
'କାଟି', 
'ମାରି', 
'ଜଳାଇ', 
'ନେଇ', 
'ଦିଶି', 
'ଖସି', 
'ଉଠେଇ', 
'ସାରି', 
'କରି', 
'ଥରି', 
'ଚାରି', 
'ଫିରି', 
'ଫିକି']

st1=' '
st1=st1.join(word1)   #converting the list into string
print(st1)

import re

def verb(st1):  

  if re.search(r'[.*]?[]$',st1):  #past tense marker
    verb1=re.add(r"[ଇ|ି]$",r"ଲି",st1) #1Psg
    return "ମୁ "+verb1

    verb2=re.add(r"[ଇ|ି]$",r"ଲା",st1) #1Ppl
    return "ଆମେ "+verb2

    verb3=re.add(r"[ଇ|ି]$",r"ଲ",st1) #2Psg
    return "ତମେ "+verb3 

    verb4=re.add(r"[ଇ|ି]$",r"ଲ",st1) #2Ppl
    return "ତମେ ମାନେ "+verb4

    verb5=re.add(r"[ଇ|ି]$",r"ଲା",st1) #3Psg
    return "ସେ "+verb5
    
    verb6=re.add(r"[ଇ|ି]$",r"ଲେ",st1) #3Ppl
    return "ସେ ମାନେ "+verb6

  verb(x)
  print("Enter the word: ",x)
return  

import re

def verb(st1):  

  if re.search(r'[.*]?[]$',st1):  #future tense marker
    verb1=re.add(r"[ଇ|ି]$",r"ବି",st1) #1Psg
    return "ମୁ "+verb1

    verb2=re.add(r"[ଇ|ି]$",r"ବା",st1) #1Ppl
    return "ଆମେ "+verb2

    verb3=re.add(r"[ଇ|ି]$",r"ବ",st1) #2Psg
    return "ତମେ "+verb3 

    verb4=re.add(r"[ଇ|ି]$",r"ବ",st1) #2Ppl
    return "ତମେ ମାନେ "+verb4

    verb5=re.add(r"[ଇ|ି]$",r"ବେ",st1) #3Psg
    return "ସେ "+verb5
    
    verb6=re.add(r"[ଇ|ି]$",r"ବେ",st1) #3Ppl
    return "ସେ ମାନେ "+verb6

  verb(x)
  print("Enter the word here: ", x)
return

import re

def verb(st1):  

  if re.search(r'[.*]?[]$',st1):  #present tense marker
    verb1=re.add(r"[ଇ|ି]$",r"ବି",st1) #1Psg
    return "ମୁ "+verb1

    verb2=re.add(r"[ଇ|ି]$",r"ବା",st1) #1Ppl
    return "ଆମେ "+verb2

    verb3=re.add(r"[ଇ|ି]$",r"ବ",st1) #2Psg
    return "ତମେ "+verb3 

    verb4=re.add(r"[ଇ|ି]$",r"ବ",st1) #2Ppl
    return "ତମେ ମାନେ "+verb4

    verb5=re.add(r"[ଇ|ି]$",r"ବେ",st1) #3Psg
    return "ସେ "+verb5
    
    verb6=re.add(r"[ଇ|ି]$",r"ବେ",st1) #3Ppl
    return "ସେ ମାନେ "+verb6

  verb(x)
  print("Enter the word here: ", x)
return
