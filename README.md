
# Working with Text

## Let's go!

As you have seen from the **Instant Data Science** lesson, programming is a powerful tool for answering questions about data.  It allows us to collect, clean up and format our data and then perform calculations on that data.  

Much of our digital information is in the form of text -- song lyrics and emails, for example. To clean up and format that text with Python, we need to become familiar with our first type of data, the string. 

### Objectives
* Working with our first data type, strings
* Learning about string methods that Python provides us
* Learning how to discover new methods

## Introduction to strings

A lot of information in the world is in the form of text. If we want to capture this information and operate on it, we should become familiar with an entire datatype in Python dedicated to it: the string.

**Note:** *If you are viewing this in markdown format (files that end in .md), the first gray box will show the **input** and what follows is the **output**. The rest of the lab(s) will follow this pattern, but we've marked the input for the first few examples with the comment `'# input'`.* 


```python
'Homer Simpson' #input
```




    'Homer Simpson'



When programmers say "string", what they mean is text.  When programmers say datatype, they just mean type of data.  We can think of 'Homer Simpson' as an instance of the string datatype.

Here is another datatype in Python, a number.


```python
3 #input
```




    3



We can discover the type of a piece of data by calling, or executing, the `type` method.  By calling or executing a method, we mean running the method so that it executes the code within it.  We'll learn more about these soon enough!

Let's look at an example below:


```python
type('Homer Simpson') #input
```




    str



We need to pay attention to what type of data we are working with because they operate differently.

For example, to initialize a string we cannot simply type letters.  Instead, we need to be very explicit with Python and tell Python it is about to see some text.  We do this by surrounding our text with quotes.  If we don't do that, or end our quotation marks too early, Python will throw us an error.


```python
'Homer Simps'on #input
```


      File "<ipython-input-5-b38f60fea49d>", line 1
        'Homer Simps'on #input
                      ^
    SyntaxError: invalid syntax



If we want, we can also use double quotes.


```python
"Homer don't care" #input
```




    "Homer don't care"



**Note:** double quotes and single quotes can be used interchangeably in Python; however, it is important that we stay consistent.

## Changing data with built in methods

Python is picky like this for a reason. Once it knows we are working with a string, it gives us specific functionality for operating on strings.  We call this functionality a function, or a method.

For example here is a method that works with a string (text), but does not work with a number.


```python
'Homer Simpson'.upper()
```




    'HOMER SIMPSON'




```python
42.upper()
```


      File "<ipython-input-8-8ab5bf46fc2d>", line 1
        42.upper()
               ^
    SyntaxError: invalid syntax



Yep.  Bad news bears.

We can operate on a datatype with the following format: 

   * [INSTANCE OF A DATATYPE] [DOT] [METHOD NAME] [PARENTHESES]

Here are some examples, which we can see follow the same format:


```python
"Homer Simpson".endswith('Simpson')
```




    True




```python
"Charles Montgomery Burns".endswith('Simpson')
```




    False



As you can see, by following the format of data-dot-method name-parentheses we can begin to operate on our data.

###  Discovering new methods

You may be starting to worry about there being too many methods to keep track of.  Let's ask Python for help with finding more information about what we can do with strings.


```python
help('strings')
```

    no Python documentation found for 'strings'
    


The `help()` word with Python comes out of the box with the language and is like an old school Alexa.  Just like an Alexa, it often doesn't understand us.  Let's follow its stern directions, and see what happens when we type in `help(str)`.

```python
help(str)
```

```python
Help on class str in module __builtin__:

class str(basestring)
 |  str(object='') -> string
 |  
 |  Return a nice string representation of the object.
 |  If the argument is a string, the return value is the same object.
 |  
 |  Method resolution order:
 |      str
 |      basestring
 |      object
 |  
 |  Methods defined here:
 |  
 |  __add__(...)
 |      x.__add__(y) <==> x+y
 |  
 |  __contains__(...)
 |      x.__contains__(y) <==> y in x
 |  
 |  __eq__(...)
 |      x.__eq__(y) <==> x==y
 |  
 |  __format__(...)
 |      S.__format__(format_spec) -> string
 |      
 |      Return a formatted version of S as described by format_spec.
 |  
 |  __ge__(...)
 |      x.__ge__(y) <==> x>=y
 |  
 |  __getattribute__(...)
 |      x.__getattribute__('name') <==> x.name
 |  
 |  __getitem__(...)
 |      x.__getitem__(y) <==> x[y]
 |  
 |  __getnewargs__(...)
 |  
 |  __getslice__(...)
 |      x.__getslice__(i, j) <==> x[i:j]
 |      
 |      Use of negative indices is not supported.
 |  
 |  
 |  __hash__(...)
 |      x.__hash__() <==> hash(x)
 |  
 |  __le__(...)
 |      x.__le__(y) <==> x<=y
 |  
 |  __len__(...)
 |      x.__len__() <==> len(x)
 |  
 |  __sizeof__(...)
 |      S.__sizeof__() -> size of S in memory, in bytes
 |  
 |  __str__(...)
 |      x.__str__() <==> str(x)
 |  
 |  capitalize(...)
 |      S.capitalize() -> string
 |      
 |      Return a copy of the string S with only its first character
 |      capitalized.
 

        ... A Lot More Code ...

```

**Note:** *In order to exit out of `help()` in your terminal, you can press the letter `q`.*

Holy cow that's a lot of words.  If we scroll down to the word capitalize, things begin to make more sense.  For example, for capitalize, this is what it says


capitalize(...)

    S.capitalize() -> str
    Return a capitalized version of S, i.e. make the first character
    have upper case and the rest lower case.

Our next step is to use our formula of datatype-dot-method name-parentheses, and see what happens next.


```python
"smithers".capitalize()
```




    'Smithers'



Excellent.  Just like we thought.

### Tips going forward 

That's really it for this lesson on strings, and it's easy to feel a little unsatisfied with just a few methods on the datatype.  What's more important with programming is mechanisms of discovery and experimentation beyond just memorizing a list of features.

In this lesson, we already saw a few of them.  
* Guess: We just tried something and looked to the error message for clues as to what to do next.
* help(str): We saw a nice way to learn about new methods, then we took a guess to test our understanding
* Following a pattern: We started with a simple method like calling upper, took a moment to break this down into a pattern, and then tried this pattern again to call other methods 

Here is one more method of discovery:  just ask Google.  For example, look what happens when we ask Google about capitalization.

![](https://learn-verified.s3.amazonaws.com/data-science-assets/ask-google.png)

[A great link with a detailed answer.](https://stackoverflow.com/a/1549644)

![](https://learn-verified.s3.amazonaws.com/data-science-assets/stack-overflow.png)

Then we try this new method out ourselves, to see if this user on StackOverFlow is right (they normally are).


```python
"hello world".title()
```




    'Hello World'



And our work is done.

Feel free to look at [other common string operations here.](https://docs.python.org/2/library/string.html)

### Summary

In this lesson, we learned about our first datatype in Python: the string.  A string is just text. We indicate to Python that we are writing a string by surrounding our content with quotation marks. Once we do this, we can operate on this string by calling methods like `upper` or `endswith`. We identified a general pattern for calling methods on datatypes: 'instance of a datatype-dot-method name-parentheses'.

The second thing we learned was different mechanisms for learning about methods.  We saw the importance of guessing and experimentation, and how doing so can give us error messages, which provide clues. We also saw how to ask questions about a datatype by calling 'help' followed by the datatype name like `help(str)`.  Finally, we saw we can ask Google.  This mechanism of exploration is a skill we'll build up over time and this course will provide guidance and practice on along the way.
