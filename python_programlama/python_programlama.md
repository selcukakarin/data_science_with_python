```python
#SAYILAR VE STRINGLERE GIRIS
9
9.2
9+9
9*9

print('HELLO AI ERA')
"HELLO AI ERA"

type(9)
type(9.2)
type("HELLO AI ERA")
```

    HELLO AI ERA





    str




```python
#STRINGLERE YAKINDAN BAKALIM

""
''

123
type(123)
"123"
type("123")

"a" + "b" 
"a" " b" 
#"a" + "-b" 

#"a" - "b" 

"a "*3
#"a"/3
```




    'a a a '




```python
#STRING METODLARI - len()

gel_yaz = "gelecegi_yazanlar"
#del mvk

a = 9
b = 10

a*b


len(gel_yaz)
len("gelecegi_yazanlar")
```




    17




```python
#STRING METODLARI - upper() & lower()

gel_yaz = "gelecegi_yazanlar"

gel_yaz.upper()
gel_yaz.lower()

gel_yaz.islower()
B = gel_yaz.upper()
```


```python
B.islower()
```




    False




```python
B.isupper()
```




    True




```python
#STRING METODLARI - replace()

gel_yaz = "gelecegi_yazanlar"

```


```python
gel_yaz.replace("e","a")
```




    'galacagi_yazanlar'




```python
gel_yaz.replace("a","i")
```




    'gelecegi_yizinlir'




```python
#STRING METODLARI - strip()

gel_yaz = " gelecegi_yazanlar "
gel_yaz.strip()
```




    'gelecegi_yazanlar'




```python
gel_yaz = "*gelecegi_yazanlar*"
gel_yaz.strip("*")
```




    'gelecegi_yazanlar'




```python
gel_yaz = "lgelecegi_yazanlarl"
gel_yaz.strip("l")
```




    'gelecegi_yazanlar'




```python
#METODLARA GENEL BAKIS

gel_yaz = "gelecegi_yazanlar"

dir(gel_yaz)
```




    ['__add__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getitem__',
     '__getnewargs__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__iter__',
     '__le__',
     '__len__',
     '__lt__',
     '__mod__',
     '__mul__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__rmod__',
     '__rmul__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'capitalize',
     'casefold',
     'center',
     'count',
     'encode',
     'endswith',
     'expandtabs',
     'find',
     'format',
     'format_map',
     'index',
     'isalnum',
     'isalpha',
     'isascii',
     'isdecimal',
     'isdigit',
     'isidentifier',
     'islower',
     'isnumeric',
     'isprintable',
     'isspace',
     'istitle',
     'isupper',
     'join',
     'ljust',
     'lower',
     'lstrip',
     'maketrans',
     'partition',
     'replace',
     'rfind',
     'rindex',
     'rjust',
     'rpartition',
     'rsplit',
     'rstrip',
     'split',
     'splitlines',
     'startswith',
     'strip',
     'swapcase',
     'title',
     'translate',
     'upper',
     'zfill']




```python
gel_yaz.capitalize()
```




    'Gelecegi_yazanlar'




```python
gel_yaz.title() 
```




    'Gelecegi_Yazanlar'




```python
#SUBSTRINGLER

gel_yaz = "gelecegi_yazanlar"

```


```python
gel_yaz[1]
```




    'e'




```python
gel_yaz[20]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-19-43a18750b209> in <module>
    ----> 1 gel_yaz[20]
    

    IndexError: string index out of range



```python
gel_yaz[0:3]
```




    'gel'




```python
#DEGISKENLER

a = 9
b = "ali_uzaya_git"
c = a*2


a/c
a*c
a*5

a = 100.2
```


```python
type(100)
```




    int




```python
type(100.2)
```




    float




```python
type(1+2j)
```




    complex




```python
#TYPE_DONUSUMLERI

toplama_bir = input()
toplama_iki = input()

type(toplama_bir)
```

    1
    2





    str




```python
toplama_bir + toplama_iki

int(toplama_bir) + int(toplama_iki)

```




    3




```python
int(11.0)

12

float(12)

type(str(12))
```




    str




```python
#print()

print("HELLO AI ERA")

print("gelecegi","yazanlar")

print("gelecegi","yazanlar", sep = "_")

print()

print()

#?print
```

    HELLO AI ERA
    gelecegi yazanlar
    gelecegi_yazanlar
    
    



```python
#VERI YAPILARI

#Listeler 

#[]
#list()

notlar = [90,80,70,50]
type(notlar)
```




    list




```python
liste = ["a",19.3,90]
list_genis = ["a",19.3,90, notlar]

len(list_genis)
```




    4




```python
list_genis[0]
list_genis[1]
list_genis[3]
```




    [90, 80, 70, 50]




```python
type(list_genis[3])
```




    list




```python
tum_liste = [liste, list_genis]
#del tum_liste
tum_liste
```




    [['a', 19.3, 90], ['a', 19.3, 90, [90, 80, 70, 50]]]




```python
#Listeler - Eleman Islemleri

liste = [10,20,30,40,50]
```


```python
liste[0]
liste[1]
```




    20




```python
liste[6]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-43-651074ede2cb> in <module>
    ----> 1 liste[6]
    

    IndexError: list index out of range



```python
liste[0:2]
```




    [10, 20]




```python
liste[:2]
```




    [10, 20]




```python
liste[2:]
```




    [30, 40, 50]




```python
yeni_liste = ["a",10,[20,30,40,50]]
yeni_liste
```




    ['a', 10, [20, 30, 40, 50]]




```python
yeni_liste[2]
```




    [20, 30, 40, 50]




```python
yeni_liste[0:2]
```




    ['a', 10]




```python
yeni_liste[2][1]
```




    30




```python
#Listeler - Eleman Degistirme

liste = ["ali","veli","berkcan","ayse"]
liste

```




    ['ali', 'veli', 'berkcan', 'ayse']




```python
liste[1] = "velinin_babasi"
liste
```




    ['ali', 'velinin_babasi', 'berkcan', 'ayse']




```python
liste[1] = "veli"
liste
```




    ['ali', 'veli', 'berkcan', 'ayse']




```python
liste[0:3] = "alinin_babasi","velinin_babasi","berkcanin_babasi"  
liste
```




    ['alinin_babasi', 'velinin_babasi', 'berkcanin_babasi', 'ayse']




```python
liste = ["ali","veli","berkcan","ayse"]
liste
```




    ['ali', 'veli', 'berkcan', 'ayse']




```python
liste = liste + ["kemal"]
liste
```




    ['ali', 'veli', 'berkcan', 'ayse', 'kemal']




```python
#del liste[2]
liste
```




    ['ali', 'veli', 'berkcan', 'ayse', 'kemal']




```python
#Listeler - Liste Metodları

liste = ["ali","veli","isik"]

dir(liste)

```




    ['__add__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__delitem__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getitem__',
     '__gt__',
     '__hash__',
     '__iadd__',
     '__imul__',
     '__init__',
     '__init_subclass__',
     '__iter__',
     '__le__',
     '__len__',
     '__lt__',
     '__mul__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__reversed__',
     '__rmul__',
     '__setattr__',
     '__setitem__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'append',
     'clear',
     'copy',
     'count',
     'extend',
     'index',
     'insert',
     'pop',
     'remove',
     'reverse',
     'sort']




```python
liste
```




    ['ali', 'veli', 'isik']




```python
#append & remove

liste.append("berkcan")

liste
```




    ['ali', 'veli', 'isik', 'berkcan']




```python
liste.remove("berkcan")
liste
```




    ['ali', 'veli', 'isik']




```python
# insert 

liste = ["ali","veli","isik"]

liste
```




    ['ali', 'veli', 'isik']




```python
liste.insert(0,"ayse")

liste
```




    ['ayse', 'ali', 'veli', 'isik']




```python
liste = ["ali","veli","isik"]

liste[0] = "ayse"

liste
```




    ['ayse', 'veli', 'isik']




```python
liste.insert(0,"ayse")
liste
```




    ['ayse', 'ayse', 'veli', 'isik']




```python
liste[1] = "ali"

liste
```




    ['ayse', 'ali', 'veli', 'isik']




```python
liste.insert(2,"mehmet")
liste
```




    ['ayse', 'ali', 'mehmet', 'veli', 'isik']




```python
liste.insert(5,"berk")
liste
```




    ['ayse', 'ali', 'mehmet', 'veli', 'isik', 'berk']




```python
len(liste)
```




    6




```python
liste.insert(len(liste),"beren")
liste
```




    ['ayse', 'ali', 'mehmet', 'veli', 'isik', 'berk', 'beren']




```python
#pop 

liste.pop(0)
liste
```




    ['ali', 'mehmet', 'veli', 'isik', 'berk', 'beren']




```python
liste.pop(4)
liste
```




    ['ali', 'mehmet', 'veli', 'isik', 'beren']




```python
#count

liste = ["ali","veli","isik","ali","veli"]
```


```python
liste.count("ali")
```




    2




```python
liste.count("veli")
```




    2




```python
liste.count("isik")
```




    1




```python
#copy

liste_yedek = liste.copy()
liste_yedek
```




    ['ali', 'veli', 'isik', 'ali', 'veli']




```python
#extend

liste.extend(["a","b",10])
liste
```




    ['ali', 'veli', 'isik', 'ali', 'veli', 'a', 'b', 10]




```python
#index()

liste.index("ali")
```




    0




```python
#reverse()

liste.reverse()
liste
```




    [10, 'b', 'a', 'veli', 'ali', 'isik', 'veli', 'ali']




```python
#sort()

liste = [10,40,5,90]
liste.sort()
liste
```




    [5, 10, 40, 90]




```python
#clear

liste.clear()
liste
```




    []




```python
#Veri Yapıları - Tuple

#Tuple Olusturma

t = ("ali","veli",1,2,3.2,[1,2,3,4])
t
```




    ('ali', 'veli', 1, 2, 3.2, [1, 2, 3, 4])




```python
t = "ali","veli",1,2,3.2, [1,2,3,4]
t
```




    ('ali', 'veli', 1, 2, 3.2, [1, 2, 3, 4])




```python
#tuple()

t = ("eleman",)
t
```




    ('eleman',)




```python
type(t)
```




    tuple




```python
#Tuple Eleman Islemleri

t = ("ali","veli",1,2,3, [1,2,3,4])
t
```




    ('ali', 'veli', 1, 2, 3, [1, 2, 3, 4])




```python
t[1]
```




    'veli'




```python
t[0:3]
```




    ('ali', 'veli', 1)




```python
t[2] = 99
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-91-17883baed432> in <module>
    ----> 1 t[2] = 99
    

    TypeError: 'tuple' object does not support item assignment



```python
# Veri Yapıları - Dictionary (Sözlük)

#Sozluk Olusturma
sozluk = {"REG" : "Regresyon Modeli",
          "LOJ" : "Lojistik Regresyon",
          "CART" : "Classification and Reg"}

sozluk
```




    {'REG': 'Regresyon Modeli',
     'LOJ': 'Lojistik Regresyon',
     'CART': 'Classification and Reg'}




```python
len(sozluk)
```




    3




```python
sozluk = {"REG" : 10,
          "LOJ" : 20,
          "CART" : 30}

sozluk
```




    {'REG': 10, 'LOJ': 20, 'CART': 30}




```python
sozluk = {"REG" : ["RMSE",10],
          "LOJ" : ["MSE", 20],
          "CART" : ["SSE",30]}

sozluk
```




    {'REG': ['RMSE', 10], 'LOJ': ['MSE', 20], 'CART': ['SSE', 30]}




```python
#Sozluk Eleman Islemleri

sozluk = {"REG" : "Regresyon Modeli",
          "LOJ" : "Lojistik Regresyon",
          "CART" : "Classification and Reg"}

sozluk[0]
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-97-e2af0c429f23> in <module>
          5           "CART" : "Classification and Reg"}
          6 
    ----> 7 sozluk[0]
    

    KeyError: 0



```python
sozluk["REG"]
```




    'Regresyon Modeli'




```python
sozluk["LOJ"]
```




    'Lojistik Regresyon'




```python
sozluk = {"REG" : ["RMSE",10],
          "LOJ" : ["MSE", 20],
          "CART" : ["SSE",30]}

sozluk["REG"]
```




    ['RMSE', 10]




```python
sozluk = {"REG" : {"RMSE": 10,
                   "MSE" : 20,
                   "SSE" : 30},

          "LOJ" : {"RMSE": 10,
                   "MSE" : 20,
                   "SSE" : 30},
                   
          "CART" : {"RMSE": 10,
                   "MSE" : 20,
                   "SSE" : 30}}

sozluk
```




    {'REG': {'RMSE': 10, 'MSE': 20, 'SSE': 30},
     'LOJ': {'RMSE': 10, 'MSE': 20, 'SSE': 30},
     'CART': {'RMSE': 10, 'MSE': 20, 'SSE': 30}}




```python
sozluk["REG"]["SSE"]
```




    30




```python
#Sozluk - Eleman Eklemek & Degistirmek

sozluk = {"REG" : "Regresyon Modeli",
          "LOJ" : "Lojistik Regresyon",
          "CART" : "Classification and Reg"}
sozluk
```




    {'REG': 'Regresyon Modeli',
     'LOJ': 'Lojistik Regresyon',
     'CART': 'Classification and Reg'}




```python
sozluk["GBM"] = "Gradient Boosting Mac"
sozluk

```




    {'REG': 'Regresyon Modeli',
     'LOJ': 'Lojistik Regresyon',
     'CART': 'Classification and Reg',
     'GBM': 'Gradient Boosting Mac'}




```python
sozluk["REG"] = "Coklu Dogrusal Regresyon"
sozluk
```




    {'REG': 'Coklu Dogrusal Regresyon',
     'LOJ': 'Lojistik Regresyon',
     'CART': 'Classification and Reg',
     'GBM': 'Gradient Boosting Mac'}




```python
sozluk[1] = "Yapay Sinir Aglari"

sozluk
```




    {'REG': 'Coklu Dogrusal Regresyon',
     'LOJ': 'Lojistik Regresyon',
     'CART': 'Classification and Reg',
     'GBM': 'Gradient Boosting Mac',
     1: 'Yapay Sinir Aglari'}




```python
l = [1]
l
```




    [1]




```python
sozluk[l] = "yeni bir sey"
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-110-afdf15b260fe> in <module>
    ----> 1 sozluk[l] = "yeni bir sey"
    

    TypeError: unhashable type: 'list'



```python
t = ("tuple",)
```


```python
sozluk[t] = "yeni bir sey"
sozluk
```




    {'REG': 'Coklu Dogrusal Regresyon',
     'LOJ': 'Lojistik Regresyon',
     'CART': 'Classification and Reg',
     'GBM': 'Gradient Boosting Mac',
     1: 'Yapay Sinir Aglari',
     ('tuple',): 'yeni bir sey'}




```python
#Veri Yapilari - Setler

#Set olusturmak

s = set()
s
```




    set()




```python
# list to set
l = [1,"a","ali", 123]
s = set(l)
s
```




    {1, 123, 'a', 'ali'}




```python
# tuple to set
t = ("a","ali")

s = set(t)
s
```




    {'a', 'ali'}




```python
ali = "lutfen_ata_bak ma_uza ya_git"
type(ali)
```




    str




```python
# str to set
s = set(ali)
s
```




    {' ',
     '_',
     'a',
     'b',
     'e',
     'f',
     'g',
     'i',
     'k',
     'l',
     'm',
     'n',
     't',
     'u',
     'y',
     'z'}




```python
l = ["ali", "lutfen", "ata", "bakma", "uzaya",
     "git", "git", "ali","git"]

l
```




    ['ali', 'lutfen', 'ata', 'bakma', 'uzaya', 'git', 'git', 'ali', 'git']




```python
# list to set
s = set(l)
s
```




    {'ali', 'ata', 'bakma', 'git', 'lutfen', 'uzaya'}




```python
len(s)
```




    6




```python
l[0]
```




    'ali'




```python
s[0]
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-125-c9c96910e542> in <module>
    ----> 1 s[0]
    

    TypeError: 'set' object is not subscriptable



```python
# Eleman ekleme & cikarma

l = ["gelecegi","yazanlar"]

s = set(l)

s
```




    {'gelecegi', 'yazanlar'}




```python
dir(s)
```




    ['__and__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__iand__',
     '__init__',
     '__init_subclass__',
     '__ior__',
     '__isub__',
     '__iter__',
     '__ixor__',
     '__le__',
     '__len__',
     '__lt__',
     '__ne__',
     '__new__',
     '__or__',
     '__rand__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__ror__',
     '__rsub__',
     '__rxor__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__sub__',
     '__subclasshook__',
     '__xor__',
     'add',
     'clear',
     'copy',
     'difference',
     'difference_update',
     'discard',
     'intersection',
     'intersection_update',
     'isdisjoint',
     'issubset',
     'issuperset',
     'pop',
     'remove',
     'symmetric_difference',
     'symmetric_difference_update',
     'union',
     'update']




```python
s.add("ile")
s
```




    {'gelecegi', 'ile', 'yazanlar'}




```python
s.add("gelecege_git")
s
```




    {'gelecege_git', 'gelecegi', 'ile', 'yazanlar'}




```python
s.add("ile")
s
```




    {'gelecege_git', 'gelecegi', 'ile', 'yazanlar'}




```python
s.remove("ali")
s
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-131-2551065c593f> in <module>
    ----> 1 s.remove("ali")
          2 s


    KeyError: 'ali'



```python
s.discard("ali")
```


```python
#Setler - Klasik Kume Islemleri

# =============================================================================
# difference() ile iki kumenin farkini ya da "-" ifadesi
# intersection() iki kume kesisimi ya da "&" ifadesi
# union() iki kumenin birlesimi
# symmetric_difference() ikisinde de olmayanlari.
# =============================================================================


#difference

set1 = set([1,3,5])
set2 = set([1,2,3])

set1.difference(set2)
```




    {5}




```python
set2.difference(set1)
```




    {2}




```python
set1.symmetric_difference(set2)
```




    {2, 5}




```python
set1 - set2
```




    {5}




```python
set2 - set1
```




    {2}




```python
#intersection & union

set1 = set([1,3,5])
set2 = set([1,2,3])

set1.intersection(set2)
```




    {1, 3}




```python
set2.intersection(set1)
```




    {1, 3}




```python
kesisim = set1 & set2
kesisim
```




    {1, 3}




```python
birlesim = set1.union(set2)
birlesim
```




    {1, 2, 3, 5}




```python
set1.intersection_update(set2)
set1
```




    {1, 3}




```python
#Set Sorgu Islemleri

set1 = set([7,8,9])
set2 = set([5,6,7,8,9,10])

#iki kumenin kesisiminin bos olup 
#olmadiginin sorgulanması

set1.isdisjoint(set2)
```




    False




```python
#bir kumenin butun elemanlarinin baska bir kume
#icerisinde yer alip almadigi

set1.issubset(set2)
```




    True




```python
#bir kumenin bir diger kumeyi kapsayip kapsamadigi

set2.issuperset(set1)
```




    True




```python
dir(str)
```




    ['__add__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getitem__',
     '__getnewargs__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__iter__',
     '__le__',
     '__len__',
     '__lt__',
     '__mod__',
     '__mul__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__rmod__',
     '__rmul__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'capitalize',
     'casefold',
     'center',
     'count',
     'encode',
     'endswith',
     'expandtabs',
     'find',
     'format',
     'format_map',
     'index',
     'isalnum',
     'isalpha',
     'isascii',
     'isdecimal',
     'isdigit',
     'isidentifier',
     'islower',
     'isnumeric',
     'isprintable',
     'isspace',
     'istitle',
     'isupper',
     'join',
     'ljust',
     'lower',
     'lstrip',
     'maketrans',
     'partition',
     'replace',
     'rfind',
     'rindex',
     'rjust',
     'rpartition',
     'rsplit',
     'rstrip',
     'split',
     'splitlines',
     'startswith',
     'strip',
     'swapcase',
     'title',
     'translate',
     'upper',
     'zfill']




```python
#FONKSIYONLARA GIRIS VE FONKSIYON OKURYAZARLIGI

print("a","b", sep = "_")
#?print
print()

len("a")
```

    a_b
    





    1




```python
#Matematiksel Islemler

4*4
4/4
5-1
6+3
3**2
3**3
```




    27




```python
#Fonksiyon Nasil Yazilir?

4**2

def kare_al(x):
    print(x**2)
    
kare_al(5)    
```

    25



```python
#Bilgi Notuyla Cikti Uretmek

def kare_al(x):
    print(x**2)
    
kare_al(5)  
```

    25



```python
def kare_al(x):
    print("Girilen Sayinin Karesi:" + str(x**2))

kare_al(3)
```

    Girilen Sayinin Karesi:9



```python
def kare_al(x):
    print("Girilen Sayi:" + 
          str(x) + 
          ", Karesi:" +
          str(x**2))

kare_al(3)
```

    Girilen Sayi:3, Karesi:9



```python
#Iki Argumanli Fonksiyon Tanimlamak

def kare_al(x):
    print(x**2)
kare_al(5)
```

    25



```python
def carpma_yap(x, y):
    print(x*y)
    
carpma_yap(2,3)
```

    6



```python
#On Tanimli Argumanlar

#?print

def carpma_yap(x, y = 1):
    print(x*y)

carpma_yap(3,4)

print("HELLO AI ERA")
```

    12
    HELLO AI ERA



```python
#Argumanlarin Siralamasi

def carpma_yap(x, y = 1):
    print(x*y)

carpma_yap(y = 2, x = 3)

carpma_yap(2,3)
```

    6
    6



```python
#Ne Zaman Fonksiyon Yazilir?

#isi, nem, sarj

(40+25)/90

```




    0.7222222222222222




```python
def direk_hesap(isi, nem, sarj):
    print((isi + nem)/sarj)

direk_hesap(25,40,70)
```

    0.9285714285714286



```python
#Ciktiyi Girdi Olarak Kullanmak

def direk_hesap(isi, nem, sarj):
    print((isi + nem)/sarj)

cikti = direk_hesap(25,40,70)
cikti
```

    0.9285714285714286



```python
print(cikti)
```

    None



```python
direk_hesap(25,40,70)*9
```

    0.9285714285714286



    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-164-bfdb06253722> in <module>
    ----> 1 direk_hesap(25,40,70)*9
    

    TypeError: unsupported operand type(s) for *: 'NoneType' and 'int'



```python
def direk_hesap(isi, nem, sarj):
    return (isi + nem)/sarj


cikti = direk_hesap(25,40,70)
cikti
```




    0.9285714285714286




```python
print(cikti)
```

    0.9285714285714286



```python
direk_hesap(25,40,70)*9
```




    8.357142857142858




```python
def direk_hesap(isi, nem, sarj):
    return (isi + nem)/sarj


direk_hesap(25,40,70)
```




    0.9285714285714286




```python
#Local ve Global Degiskenler

x = 10
y = 20

def carpma_yap(x = 2,y = 1):
    return x*y


carpma_yap(2,3)

```




    6




```python
#Local Etki Alanindan Global Etki Alanini Degistirmek

x = []
#del x

def eleman_ekle(y):
    x.append(y)
    print(str(y) + " ifadesi eklendi")

eleman_ekle("ali")
```

    ali ifadesi eklendi



```python
eleman_ekle("veli")
```

    veli ifadesi eklendi



```python
x
```




    ['ali', 'veli', 'veli']




```python
# KARAR & KONTROL YAPILARI


#True-False Sorgulamaları

sinir = 5000
```


```python
sinir == 4000
```




    False




```python
sinir == 5000
```




    True




```python
5 == 4
```




    False




```python
5 == 5
```




    True




```python
#if

sinir = 50000
gelir = 60000
```


```python
gelir < sinir
```




    False




```python
if gelir < sinir:
    print("Gelir sinirdan kucuk")
```


```python
if gelir > sinir:
    print("Gelir sinirdan buyuk")
```

    Gelir sinirdan buyuk



```python
#else

sinir = 50000
gelir = 35000
    
if gelir > sinir:
    print("Gelir sinirdan buyuk")
else:
    print("Gelir sinirdan kucuk")    

```

    Gelir sinirdan kucuk



```python
#diger ornek
sinir = 50000
gelir = 50000
    
if gelir == sinir:
    print("Gelir sinira esittir")
else:
    print("Gelir sinira esit degildir")  

```

    Gelir sinira esittir



```python
#elif

sinir = 50000
gelir1 = 60000
gelir2 = 50000
gelir3 = 35000
    
if gelir1 > sinir:
    print("Tebrikler, hediye kazandiniz.")
elif gelir1 < sinir:
    print("Uyari!")
else:
    print("Takibe devam")  


if gelir3 > sinir:
    print("Tebrikler, hediye kazandiniz.")
elif gelir3 < sinir:
    print("Uyari!")
else:
    print("Takibe devam")  


if gelir2 > sinir:
    print("Tebrikler, hediye kazandiniz.")
elif gelir2 < sinir:
    print("Uyari!")
else:
    print("Takibe devam")  
```

    Tebrikler, hediye kazandiniz.
    Uyari!
    Takibe devam



```python
#mini uygulama
sinir = 50000
magaza_adi = input("Magaza Adi Nedir?")
gelir = int(input("Gelirinizi Giriniz:"))

if gelir > sinir:
    print("Tebrikler:" + magaza_adi + " promosyon kazandiniz!")
elif gelir < sinir:
    print("Uyari! Cok dusuk gelir:" + str(gelir))
else:
    print("Takibe devam")
```

    Magaza Adi Nedir?selcuk
    Gelirinizi Giriniz:1
    Uyari! Cok dusuk gelir:1



```python
#DONGULER - for

ogrenci = ["ali","veli","isik","berk"]

ogrenci[0]
ogrenci[1]
ogrenci[2]
ogrenci[3]

for i in ogrenci:
    print(i)

```

    ali
    veli
    isik
    berk



```python
#for - devam

maaslar = [1000,2000,3000,4000,5000]

maaslar[0]
maaslar[1]
maaslar[2]
maaslar[3]
maaslar[4]

for maas in maaslar:
    print(maas)
```

    1000
    2000
    3000
    4000
    5000



```python
#dongu ve fonksiyonları birlikte kullanmak

def kare_al(x):
    print(x**2)    
    
kare_al(2)    
```

    4



```python
maaslar = [1000,2000,3000,4000,5000]

for i in maaslar:
    print(i)
```

    1000
    2000
    3000
    4000
    5000



```python
#maaslara yuzde 20 zam yapilacak gerekli kodlari
#yaziniz.

1000*20/100  + 1000   

maaslar[0]*20/100 + maaslar[0]
maaslar[1]*20/100 + maaslar[1]
maaslar[2]*20/100 + maaslar[2]    
```




    3600.0




```python
#dongu yazilacak   
#fonksiyon yazmak 
    
def yeni_maas(x):
    print(x)

yeni_maas(4)
```

    4



```python
def yeni_maas(x):
    print(x*20/100 + x)
    
yeni_maas(1000)
```

    1200.0



```python
yeni_maas(2000)
```

    2400.0



```python
yeni_maas(3000)

```

    3600.0



```python
maaslar = [1000,2000,3000,4000,5000]
for i in maaslar:
    yeni_maas(i)
```

    1200.0
    2400.0
    3600.0
    4800.0
    6000.0



```python
#mini uygulama
#if, for ve fonksiyonlari birlikte kullanmak    

maaslar = [1000,2000,3000,4000,5000]

def maas_ust(x):
    print(x*10/100 + x)

def maas_alt(x):
    print(x*20/100 + x)

for i in maaslar:
    if i >= 3000:
        maas_ust(i)
    else:
        maas_alt(i)
```

    1200.0
    2400.0
    3300.0
    4400.0
    5500.0



```python
#break & continue
        
maaslar = [8000,5000,2000,1000,3000, 7000, 1000]
```


```python
dir(maaslar)
```




    ['__add__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__delitem__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getitem__',
     '__gt__',
     '__hash__',
     '__iadd__',
     '__imul__',
     '__init__',
     '__init_subclass__',
     '__iter__',
     '__le__',
     '__len__',
     '__lt__',
     '__mul__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__reversed__',
     '__rmul__',
     '__setattr__',
     '__setitem__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'append',
     'clear',
     'copy',
     'count',
     'extend',
     'index',
     'insert',
     'pop',
     'remove',
     'reverse',
     'sort']




```python
maaslar.sort()
maaslar
```




    [1000, 1000, 2000, 3000, 5000, 7000, 8000]




```python
for i in maaslar:
    if i == 3000:
        print("kesildi")
        break
    print(i)
```

    1000
    1000
    2000
    kesildi



```python
for i in maaslar:
    if i == 3000:
        continue
    print(i)
```

    1000
    1000
    2000
    5000
    7000
    8000



```python
#while

sayi = 1

while sayi < 9:
    sayi += 1
    print(sayi)

```

    2
    3
    4
    5
    6
    7
    8
    9



```python
#NESNE YONELIMLI PROGRAMLAMA - OOP

#Sinif Nedir?
    

#Sinif Ozellikleri (Class attributes)

class VeriBilimci():
    bolum = ''
    sql = 'Evet'
    deneyim_yili = 0
    bildigi_diller = []
    
```


```python
#Siniflarin ozelliklerine erismek
VeriBilimci.bolum
```




    ''




```python
VeriBilimci.sql
```




    'Evet'




```python
#siniflarin ozelliklerini degistirmek
VeriBilimci.sql = "Hayir"
VeriBilimci.sql
```




    'Hayir'




```python
#Sinif Orneklendirmesi (instantiation)

ali = VeriBilimci()
```


```python
ali.sql
```




    'Hayir'




```python
ali.deneyim_yili
```




    0




```python
ali.bolum
```




    ''




```python
ali.bildigi_diller.append("Python")
ali.bildigi_diller
```




    ['Python']




```python
veli = VeriBilimci()
veli.sql
```




    'Hayir'




```python
veli.bildigi_diller
```




    ['Python']




```python
#Ornek ozellikleri

class VeriBilimci():
    bildigi_diller = ["R","PYTHON"]
    bolum = ''
    sql = ''
    deneyim_yili = 0
    def __init__(self):
        self.bildigi_diller = []
        self.bolum = ''
```


```python
ali = VeriBilimci()
ali.bildigi_diller
```




    []




```python
veli = VeriBilimci()
veli.bildigi_diller
```




    []




```python
ali.bildigi_diller.append("Python")
ali.bildigi_diller
```




    ['Python', 'Python']




```python
veli.bildigi_diller
```




    []




```python
veli.bildigi_diller.append("R")
veli.bildigi_diller
```




    ['R']




```python
VeriBilimci.bildigi_diller
```




    ['R', 'PYTHON']




```python
ali.bolum
```




    ''




```python
VeriBilimci.bolum
```




    ''




```python
ali.bolum = "istatistik"
```


```python
VeriBilimci.bolum
```




    ''




```python
veli.bolum
```




    ''




```python
veli.bolum = "end_muh"
veli.bolum
```




    'end_muh'




```python
ali.bolum
```




    'istatistik'




```python
VeriBilimci.bolum
```




    ''




```python
#Ornek Metodlari

class VeriBilimci():
    calisanlar = []
    def __init__(self):
        self.bildigi_diller = []
        self.bolum = ''
    def dil_ekle(self, yeni_dil) :
        self.bildigi_diller.append(yeni_dil)


ali = VeriBilimci()
ali.bildigi_diller
```




    []




```python
ali.bolum
```




    ''




```python
veli = VeriBilimci()
veli.bildigi_diller
```




    []




```python
veli.bolum
```




    ''




```python
dir(VeriBilimci)
```




    ['__class__',
     '__delattr__',
     '__dict__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__le__',
     '__lt__',
     '__module__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     '__weakref__',
     'calisanlar',
     'dil_ekle']




```python
VeriBilimci.dil_ekle
```




    <function __main__.VeriBilimci.dil_ekle(self, yeni_dil)>




```python
VeriBilimci.dil_ekle("R")
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-256-cab02c249a69> in <module>
    ----> 1 VeriBilimci.dil_ekle("R")
    

    TypeError: dil_ekle() missing 1 required positional argument: 'yeni_dil'



```python
ali.dil_ekle("R")
```


```python
ali.bildigi_diller
```




    ['R']




```python
veli.dil_ekle("Python")
veli.bildigi_diller
```




    ['Python']




```python
#Miras Yapilari (inheritance)

class Employees():
    def __init__(self):
        self.FirstName = ""
        self.LastName = ""
        self.Address = ""

class DataScience(Employees):
    def __init__(self):
        self.Programming = ""

veribilimci1 = DataScience()
#veribilimci1.

class Marketing(Employees):
    def __init__(self):
        self.StoryTelling = ""

mar1 = Marketing()
#mar1.


class Employee_yeni():
    def __init__(self, FirstName,LastName,Address):
        self.FirstName = FirstName
        self.LastName = LastName
        self.Address = Address


ali = Employee_yeni("a","b","c")
ali.FirstName


```




    'a'




```python
#Python'da Fonksiyonel Programlama

#Fonksiyonlar dilin bastacidir. 
#(Birinci sinif nesnelerdir)
#Yan etkisiz fonksiyonlar. (stateless, girdi-cikti)
#Yuksek seviye fonksiyonlar.
#Vektorel operasyonlar.


#Yan Etkisiz Fonksiyonlar (Pure Functions)

#Ornek1:Bagimsizlik

A = 9

def impure_sum(b):
    return b + A

def pure_sum(a,b):
    return a + b


impure_sum(6)
```




    15




```python
pure_sum(3,4)
```




    7




```python
#Ornek2: Olumcul yan etkiler
#OOP
class LineCounter:
    def __init__(self, filename):
        self.file = open(filename, 'r')
        self.lines = []
    
    def read(self):
        self.lines = [line for line in self.file]
    
    def count(self):
        return len(self.lines)


lc = LineCounter('deneme.txt') 

print(lc.lines) 
```

    []



```python
print(lc.count())
```

    0



```python
lc.read()
```


```python
print(lc.lines)
```

    ['selçuk\n', 'akarın\n', '123\n', '321']



```python
print(lc.count())
```

    4



```python
#FP

def read(filename):
  with open(filename, 'r') as f:
      return [line for line in f]

def count(lines):
  return len(lines)

example_lines = read('deneme.txt')
example_lines
```




    ['selçuk\n', 'akarın\n', '123\n', '321']




```python
lines_count = count(example_lines)
lines_count
```




    4




```python
#Vektorel Operasyonlar (Vectorel Operations)
#OOP
a = [1,2,3,4]
b = [2,3,4,5]

ab = []

range(0, len(a))

for i in range(0, len(a)):
    ab.append(a[i]*b[i])

ab
```




    [2, 6, 12, 20]




```python
#FP

import numpy as np
a = np.array([1,2,3,4])
b = np.array([2,3,4,5])

a*b
```




    array([ 2,  6, 12, 20])




```python
#Isimsiz Fonksiyonlar (Anonymous Functions)


def old_sum(a,b):
    return a + b

old_sum(4,5)
```




    9




```python
new_sum = lambda a,b: a + b
new_sum(4,5)
```




    9




```python
sirasiz_liste = [('b', 3), ('a', 8), ('d', 12), ('c', 1)]
sirasiz_liste
```




    [('b', 3), ('a', 8), ('d', 12), ('c', 1)]




```python
sorted(sirasiz_liste, key = lambda x: x[1])
```




    [('c', 1), ('b', 3), ('a', 8), ('d', 12)]




```python
#map & filter & reduce 

liste = [1,2,3,4,5]

for i in liste:
    print(i+ 10)
```

    11
    12
    13
    14
    15



```python
list(map(lambda x: x*10, liste))
```




    [10, 20, 30, 40, 50]




```python
#filter

liste = [1,2,3,4,5,6,7,8,9,10]

list(filter(lambda x: x % 2 == 0, liste))
```




    [2, 4, 6, 8, 10]




```python
#reduce

from functools import reduce

liste = [1,2,3,4]
reduce(lambda a,b: a + b, liste)

```




    10




```python
#Modul Olusturmak

#HesapModulu.py
def yeni_maas(x):
    print(x*20/100 + x)
    
maaslar = [1000,2000,3000,4000]  
```


```python
#test
import HesapModulu 
HesapModulu.yeni_maas(1000)


import HesapModulu as hm
hm.yeni_maas(2000)

from HesapModulu import yeni_maas
yeni_maas(3000)

import HesapModulu as hm
hm.maaslar
```


    ---------------------------------------------------------------------------

    ModuleNotFoundError                       Traceback (most recent call last)

    <ipython-input-46-4643ffcb5f13> in <module>()
          1 #test
    ----> 2 import HesapModulu
          3 HesapModulu.yeni_maas(1000)
          4 
          5 


    ModuleNotFoundError: No module named 'HesapModulu'



```python
#Hatalar / istisnalar (exceptions)

#ZeroDivisionError hatasi
a = 10
b = 0

a/b


try:
    print(a/b)
except ZeroDivisionError:
    print("Payda da sifir olmaz")
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-47-ace111fa3ae7> in <module>()
          5 b = 0
          6 
    ----> 7 a/b
          8 
          9 


    ZeroDivisionError: division by zero



```python
#tip hatasi
    
a = 10    
b = "2"

a / b

try:
    print(a/b)
except TypeError:
    print("Sayi ve string problemi")


a = 10    
b = 2

a / b

try:
    print(a/b)
except TypeError:
    print("Sayi ve string problemi")


```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-49-3b06ad36f98e> in <module>()
          4 b = "2"
          5 
    ----> 6 a / b
          7 
          8 try:


    TypeError: unsupported operand type(s) for /: 'int' and 'str'



```python

a = [13, 10, 15, 12, 17, 12, 19, 18, 11, 12, 190]
a.sort()
a


a
import numpy as np
np.median(a)

```




    13.0




```python

```
