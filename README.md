# Assignment #5 & #6 - March 4th to March 18

###### *Solutions for previous assignments can be found here: https://github.com/ponceoscarj/nlp_python_pilot/tree/main*


## Overall Instructions
1. Watch the following video:
    1. Lecture 6: Recursion and Dictionaries. [[Link]](https://ocw.mit.edu/courses/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/resources/lecture-6-recursion-and-dictionaries/)
    2. Lecture 7: Testing, Debugging, Exceptions, and Assertions. [[Link]](https://ocw.mit.edu/courses/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/resources/lecture-7-testing-debugging-exceptions-and-assertions/)
    3. Lecture 8: Object Oriented Programming. [[Link]](https://ocw.mit.edu/courses/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/resources/lecture-8-object-oriented-programming/)
    4. Lecture 9: Python Classes and Inheritance [[Link]](https://ocw.mit.edu/courses/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/resources/lecture-9-python-classes-and-inheritance/)


## Python assignment

### Rules:
- Do not use external packages (i.e., regex) **EXCEPT** for the last question (It's more challenging if you do not use external packages)

### Submission format:
- Submit your two python scripts to your classroom repository
- Organise your coding by question (e.g., Q1)

### 1. Create a function that converts a list into a dictionary: 
You have to create a function that has two input parameters and returns a dictionary with one key (a string) and one value (a list).

input parameters:
```python
pos = "noun"
items = ["park", "football", "home", "Switzerland"]
```

output (return):
```python
{'noun': ['park', 'football', 'home', 'Switzerland']}
```

Example:
Your function should look like the code below. You have to replace the underscores with your coding, it can be one line or multiple lines, it's up to you.
```python
def convert_lst_dct(pos, items):
    ______
    ______
    ______
    ______
    return new_dct
```

### 2. Create a function that generates your part-of-speech (POS) grammar:  
Create a function that create a dictionary with multiple keys.

Input parameters:
```python
pos = ["noun", "pronoun", "preposition"]
values_list = [["park", "football", "home", "Switzerland"], 
               ["i", "me", "he", "she"],
               ["to","at"]]
```
output:
```python
grammar = {"noun":["park", "football", "home", "Switzerland"], 
"pronoun":["i", "me", "he", "she"], 
"preposition": ["to","at"]}
```



### 3. Create a function that identifies the part-of-speech (POS) of a sentence - List of lists:  
The function will input a sentence (`str`) and a grammar (`dict`) and it will automatically classify each word's POS based on your grammar and the function will output a list of lists (See outuput).


Input parameters:
```python
sentence = "I want to play football"
grammar = {"noun":["park", "football", "home", "Switzerland"], 
        "pronoun":["i", "me", "he", "she"],
        "verb":["work", "want", "play", "travel"], 
        "preposition": ["to","at"]}
```

Output:
```python
[['pronoun', 'i'], ['verb', 'want'], ['preposition', 'to'], ['verb', 'play'], ['noun', 'football']]
```

As you see each list has the word and their corresponding POS in the following form `[POS, word]`.

### 4. Create a function that identifies the part-of-speech (POS) of a sentence - Dictionary:  
Same as question 3 but this time your output will be a dictionary where the keys are the words and the values are their corresponding POS. See below.

Input parameters:
```python
sentence = "I want to play football"
grammar = {"noun":["park", "football", "home", "Switzerland"], 
        "pronoun":["i", "me", "he", "she"],
        "verb":["work", "want", "play", "travel"], 
        "preposition": ["to","at"]}
```

Output:
```python
{'i': 'pronoun', 'want': 'verb', 'to': 'preposition', 'play': 'verb', 'football': 'noun'}
```

As you can see the keys and values are organised in the following form `{word: POS, word: POS, word:POS ...}`

### 5. Create a class that has two main methods and an `__init__` method  
In this question you have to combine what you did on **Question 3** and **Question 4**. 

Your class name will be `pos_tag` without any parent. It has to be initialised with `grammar`: 

```python
grammar = {"noun":["park", "football", "home", "Switzerland"], 
        "pronoun":["i", "me", "he", "she"],
        "verb":["work", "want", "play", "travel"], 
        "preposition": ["to","at"]}
```

Within your class, you will have two methods : `pos_lst` and `pos_dct`. The first (`pos_lst`) will do the same as in your **Question 3** and the second (`pos_dct`) will do the same as in your **Question 4**. For each method, there should be only one input parameter `sentence` in the form of string. 

Example
```python
# one of your methods within your class should look like this
def pos_dct(self, sentence):
    ...
    ...
    return ...
```

After you create your `pos_tag` class you should be able to run the following code without problems (errors):

```python
pos_class = pos_tag(grammar) # This instantiates your class


sentence = "I want to play football" # you need a sentence for your two methods
lst_pos_result = pos_class.pos_lst(sentence) 
dct_pos_result = pos_class.pos_dct(sentence) 

print(lst_pos_result)
print(dct_pos_result)
```

### 6. Using assertion and exception
Introduce one `assert` to make sure that the `grammar` input is a dictionary `dict`.

Also, `raise` an error called `ZeroDivisionError` to make sure your `sentence` has at least one character or word (it is not empty or `""`). I would recommend trying a condition where you divide 1 by the number of words/strings of the sentence. If the sentence has no strings (characters or words), the length should be 0 and dividing 1 by 0 should raise the `ZeroDivisionError`. 

### 7. Creating a `__str__` method
Create a print or `__str__` method so that your `pos_class` class does the following:

Input:
```python
print(pos_class)
```

Output:
```
The given grammar is {'noun': ['park', 'football', 'home', 'Switzerland'], 'pronoun': ['i', 'me', 'he', 'she'], 'verb': ['work', 'want', 'play', 'travel'], 'preposition': ['to', 'at']}
```


### 8. Reorganise your python script
Rename the python script you have been working with to `pos_script.py` and organise it with `if __name__ == "__main__"`. It is a good practice to do this with **ALL** of your future python scripts.

For example, the code below (totally unrelated to this assignment) shows how your script should be reorganised:

```python
def echo(text: str, repetitions: int = 3) -> str:
    """Imitate a real-world echo."""
    echoed_text = ""
    for i in range(repetitions, 0, -1):
        echoed_text += f"{text[-i:]}\n"
    return f"{echoed_text.lower()}."

if __name__ == "__main__":
    text = input("Yell something at a mountain: ")
    print(echo(text))
```

As you can see all functions and classes go before the `if __name__ == "__main__"`. If you want to call any of the functions or classes, you should put these after the ``if __name__ == "__main__"`` and they have to be indented 1 `tab` or 4 `spaces` to the right. Pay close attention to the indentation!!

Therefore, your functions and classes from Question 1 to Question 7 should go before `if __name__ == "__main__"` and your answers (including printing) should be located after this. 

Example:
```python
def convert_lst_dct(pos, items): # obtained from Question 1
    ______
    ______
    ______
    return new_dct


if __name__ == "__main__":
    #Q1
    noun = ["park", "football", "home", "Switzerland"]
    print(convert_lst_dct("noun", noun))
    
```

Understanding ``if __name__ == "__main__"`` is extremely important for Object-oriented programming (OOP) and it will be helpful for your final python assignment. If you want a more thorough explanation, please visit this site (subscription is free): https://realpython.com/if-name-main-python/ 

### 9. Using your class from another script
Create a new script called `new_script.py` and call your already created `pos_tag` class. You call this class at the beginning of your coding. A brief description of how to do this is given below.

```python
from file_name import function_name
# file_name is the name of the file where the class/function you are interested in is located.
# As you see file_name does not have the .py extension
# function_name is the name of the class/function you want to import
```

From now onwards you will only be working on your  `new_script.py` file. As you know, it is a good practice to use `if __name__ == "__main__":` Do not forget to add this into this new script. To make sure calling your class from your new script is working the coding below should run in your `new_script.py` without problems/errrors.

Input:
```python
sentence = "I want to stay at home"
grammar = {"noun":["park", "football", "home", "Switzerland"], 
            "pronoun":["i", "me", "he", "she"],
            "verb":["work", "want", "play", "travel", "stay"], 
            "preposition": ["to","at"]}

new_pos_class = pos_tag(sentence, grammar)
print(new_pos_class)
```

Output:
```python
The original sentence is "I want to stay at home"
The grammar is {'noun': ['park', 'football', 'home', 'Switzerland'], 'pronoun': ['i', 'me', 'he', 'she'], 'verb': ['work', 'want', 'play', 'travel', 'stay'], 'preposition': ['to', 'at']}
```

### 10. Inheritance
___About creating your new class___:
In your `new_script.py` create a new class called `multiple_pos` that inherits all attributes from `pos_tag`. Your `multiple_pos` should only initialise with a dictionary (e.g., see `grammar` below).  Lastly, I would recommend calling the `pos_tag` constructor within your `multiple_pos` `__init__` method (slide 19 - lecture 9), but feel free to do what works best for you. 

___About the method within your new class___:
Your `multiple_pos` should have a method called `accum_sent_pos` that allows you to introduce a sentence (new parameter) in the form of string `str`. Every word of this sentence should be tagged with its corresponding POS with the function `pos_dct` from the parent class or `pos_tag`.  Once the sentence is POS-tagged the result should accummulate (appended) into a list. This means that every time you input a sentence into this method, the POS-tagged sentence will accummulate into this list. See the output below to understand how it should look.  I would recommend looking at the code below, try to understand it and then re-read the instruction. **Hint: method `add_friend` from the `Person` class in slide 19,Lecture 9 does something similar**

___About printing your new class___:
Create another method that allows you to output the accummulated list when you print the `multiple_pos` class (i.e., `print(run_multiple_pos)`). 

___Testing your class___:
You should be able to run the following code without errors.

Inputs:
```python
sentences = ["I want to stay at home", 
                "I want to play football",
                "I work at home"]
grammar = {"noun":["park", "football", "home", "Switzerland"], 
        "pronoun":["i", "me", "he", "she"],
        "verb":["work", "want", "play", "travel", "stay"], 
        "preposition": ["to","at"]}

run_multiple_pos = multiple_pos(grammar)  # instantiating your new multiple_pos class

for sent in sentences:
    run_multiple_pos.accum_sent_pos(sent)

print(run_multiple_pos)
```

Output:
```python
[{'i': 'pronoun', 'want': 'verb', 'to': 'preposition', 'stay': 'verb', 'at': 'preposition', 'home': 'noun'}, {'i': 'pronoun', 'want': 'verb', 'to': 'preposition', 'play': 'verb', 'football': 'noun'}, {'i': 'pronoun', 'work': 'verb', 'at': 'preposition', 'home': 'noun'}] # If you look closely, this is a list of dictionaries
```


### 11. [OPTIONAL] Working with patient-doctor conversations
You are free to use packages. However, bear in mind that it is possible to do this question without importing external packages.

Create a class the following two things (five different methods):
- Reads the `day1_consultation01.txt` file that has a patient-doctor mock conversation.
- Splits the `day1_consultation01.txt` file into two and with a `setter method` (slide 9 - Lecture 9) creates two data attributes that are lists. One list has all turns spoken by patients and the other has all all turns spoken by doctors. 

Create a child class that inherents from your previous class and that does the following:
- Counts the number of turns made by patients 
- Counts the number of turns made by doctors
- Counts the total number of words spoken by doctors
- Counts the total number of words spoken by patients
