
# Why use code

## Let's go!

As you have seen from the **Instant Data Science** lesson, programming is a powerful tool for answering questions about data.  It allows us to collect, clean up and format our data and then perform calculations on that data.  

Much of our digital information is in the form of text.  Song lyrics and emails, for example. To clean up and format that text with Python, we need to become familiar with our first type of data, the string. 

### Objectives
* Working with our first data type, strings
* Learning about string methods that Python provides us
* Learning how to discover new methods

## Working with text

A lot of information in the world is in the form of text. If we want to capture this information and operate on it, we should become familiar with an entire datatype in Python dedicated to it: the string.

**Note:** *If you are viewing this in markdown format (files that end in .md), the first gray box will show the **input** and what follows is the **output**. The rest of the lab(s) will follow this pattern, but we've marked the input for the first few examples with a comment.* 


```python
'Homer Simpson' #input
```




    'Homer Simpson'



When programmers say "string", what they mean is text.  When programmers say datatype, they just mean type of data.  For example, here is another datatype in Python, a number.


```python
3 #input
```




    3



We can discover the type of a piece of data by calling the `type` method.


```python
type('Homer Simpson') #input
```




    str



We pay attention to what type of data we are working with because they operate differently.

For example, to initialize a string we cannot simply type letters.  Instead, we need to be very explicit with Python and tell Python it is about to see some text.  We do this by surrounding our text with quotes.  If we don't do that, or end our quotation marks too early, Python will throw us an error.


```python
'Homer Simps'on #input
```


      File "<ipython-input-5-b38f60fea49d>", line 1
        'Homer Simps'on #input
                      ^
    SyntaxError: invalid syntax



If you want, you can also use double quotes.


```python
"Homer don't care" #input
```




    "Homer don't care"



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

   * [DATATYPE] [DOT] [METHOD NAME] [PARENTHESES]

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
     |  __gt__(...)
     |      x.__gt__(y) <==> x>y
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
     |  __lt__(...)
     |      x.__lt__(y) <==> x<y
     |  
     |  __mod__(...)
     |      x.__mod__(y) <==> x%y
     |  
     |  __mul__(...)
     |      x.__mul__(n) <==> x*n
     |  
     |  __ne__(...)
     |      x.__ne__(y) <==> x!=y
     |  
     |  __repr__(...)
     |      x.__repr__() <==> repr(x)
     |  
     |  __rmod__(...)
     |      x.__rmod__(y) <==> y%x
     |  
     |  __rmul__(...)
     |      x.__rmul__(n) <==> n*x
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
     |  
     |  center(...)
     |      S.center(width[, fillchar]) -> string
     |      
     |      Return S centered in a string of length width. Padding is
     |      done using the specified fill character (default is a space)
     |  
     |  count(...)
     |      S.count(sub[, start[, end]]) -> int
     |      
     |      Return the number of non-overlapping occurrences of substring sub in
     |      string S[start:end].  Optional arguments start and end are interpreted
     |      as in slice notation.
     |  
     |  decode(...)
     |      S.decode([encoding[,errors]]) -> object
     |      
     |      Decodes S using the codec registered for encoding. encoding defaults
     |      to the default encoding. errors may be given to set a different error
     |      handling scheme. Default is 'strict' meaning that encoding errors raise
     |      a UnicodeDecodeError. Other possible values are 'ignore' and 'replace'
     |      as well as any other name registered with codecs.register_error that is
     |      able to handle UnicodeDecodeErrors.
     |  
     |  encode(...)
     |      S.encode([encoding[,errors]]) -> object
     |      
     |      Encodes S using the codec registered for encoding. encoding defaults
     |      to the default encoding. errors may be given to set a different error
     |      handling scheme. Default is 'strict' meaning that encoding errors raise
     |      a UnicodeEncodeError. Other possible values are 'ignore', 'replace' and
     |      'xmlcharrefreplace' as well as any other name registered with
     |      codecs.register_error that is able to handle UnicodeEncodeErrors.
     |  
     |  endswith(...)
     |      S.endswith(suffix[, start[, end]]) -> bool
     |      
     |      Return True if S ends with the specified suffix, False otherwise.
     |      With optional start, test S beginning at that position.
     |      With optional end, stop comparing S at that position.
     |      suffix can also be a tuple of strings to try.
     |  
     |  expandtabs(...)
     |      S.expandtabs([tabsize]) -> string
     |      
     |      Return a copy of S where all tab characters are expanded using spaces.
     |      If tabsize is not given, a tab size of 8 characters is assumed.
     |  
     |  find(...)
     |      S.find(sub [,start [,end]]) -> int
     |      
     |      Return the lowest index in S where substring sub is found,
     |      such that sub is contained within S[start:end].  Optional
     |      arguments start and end are interpreted as in slice notation.
     |      
     |      Return -1 on failure.
     |  
     |  format(...)
     |      S.format(*args, **kwargs) -> string
     |      
     |      Return a formatted version of S, using substitutions from args and kwargs.
     |      The substitutions are identified by braces ('{' and '}').
     |  
     |  index(...)
     |      S.index(sub [,start [,end]]) -> int
     |      
     |      Like S.find() but raise ValueError when the substring is not found.
     |  
     |  isalnum(...)
     |      S.isalnum() -> bool
     |      
     |      Return True if all characters in S are alphanumeric
     |      and there is at least one character in S, False otherwise.
     |  
     |  isalpha(...)
     |      S.isalpha() -> bool
     |      
     |      Return True if all characters in S are alphabetic
     |      and there is at least one character in S, False otherwise.
     |  
     |  isdigit(...)
     |      S.isdigit() -> bool
     |      
     |      Return True if all characters in S are digits
     |      and there is at least one character in S, False otherwise.
     |  
     |  islower(...)
     |      S.islower() -> bool
     |      
     |      Return True if all cased characters in S are lowercase and there is
     |      at least one cased character in S, False otherwise.
     |  
     |  isspace(...)
     |      S.isspace() -> bool
     |      
     |      Return True if all characters in S are whitespace
     |      and there is at least one character in S, False otherwise.
     |  
     |  istitle(...)
     |      S.istitle() -> bool
     |      
     |      Return True if S is a titlecased string and there is at least one
     |      character in S, i.e. uppercase characters may only follow uncased
     |      characters and lowercase characters only cased ones. Return False
     |      otherwise.
     |  
     |  isupper(...)
     |      S.isupper() -> bool
     |      
     |      Return True if all cased characters in S are uppercase and there is
     |      at least one cased character in S, False otherwise.
     |  
     |  join(...)
     |      S.join(iterable) -> string
     |      
     |      Return a string which is the concatenation of the strings in the
     |      iterable.  The separator between elements is S.
     |  
     |  ljust(...)
     |      S.ljust(width[, fillchar]) -> string
     |      
     |      Return S left-justified in a string of length width. Padding is
     |      done using the specified fill character (default is a space).
     |  
     |  lower(...)
     |      S.lower() -> string
     |      
     |      Return a copy of the string S converted to lowercase.
     |  
     |  lstrip(...)
     |      S.lstrip([chars]) -> string or unicode
     |      
     |      Return a copy of the string S with leading whitespace removed.
     |      If chars is given and not None, remove characters in chars instead.
     |      If chars is unicode, S will be converted to unicode before stripping
     |  
     |  partition(...)
     |      S.partition(sep) -> (head, sep, tail)
     |      
     |      Search for the separator sep in S, and return the part before it,
     |      the separator itself, and the part after it.  If the separator is not
     |      found, return S and two empty strings.
     |  
     |  replace(...)
     |      S.replace(old, new[, count]) -> string
     |      
     |      Return a copy of string S with all occurrences of substring
     |      old replaced by new.  If the optional argument count is
     |      given, only the first count occurrences are replaced.
     |  
     |  rfind(...)
     |      S.rfind(sub [,start [,end]]) -> int
     |      
     |      Return the highest index in S where substring sub is found,
     |      such that sub is contained within S[start:end].  Optional
     |      arguments start and end are interpreted as in slice notation.
     |      
     |      Return -1 on failure.
     |  
     |  rindex(...)
     |      S.rindex(sub [,start [,end]]) -> int
     |      
     |      Like S.rfind() but raise ValueError when the substring is not found.
     |  
     |  rjust(...)
     |      S.rjust(width[, fillchar]) -> string
     |      
     |      Return S right-justified in a string of length width. Padding is
     |      done using the specified fill character (default is a space)
     |  
     |  rpartition(...)
     |      S.rpartition(sep) -> (head, sep, tail)
     |      
     |      Search for the separator sep in S, starting at the end of S, and return
     |      the part before it, the separator itself, and the part after it.  If the
     |      separator is not found, return two empty strings and S.
     |  
     |  rsplit(...)
     |      S.rsplit([sep [,maxsplit]]) -> list of strings
     |      
     |      Return a list of the words in the string S, using sep as the
     |      delimiter string, starting at the end of the string and working
     |      to the front.  If maxsplit is given, at most maxsplit splits are
     |      done. If sep is not specified or is None, any whitespace string
     |      is a separator.
     |  
     |  rstrip(...)
     |      S.rstrip([chars]) -> string or unicode
     |      
     |      Return a copy of the string S with trailing whitespace removed.
     |      If chars is given and not None, remove characters in chars instead.
     |      If chars is unicode, S will be converted to unicode before stripping
     |  
     |  split(...)
     |      S.split([sep [,maxsplit]]) -> list of strings
     |      
     |      Return a list of the words in the string S, using sep as the
     |      delimiter string.  If maxsplit is given, at most maxsplit
     |      splits are done. If sep is not specified or is None, any
     |      whitespace string is a separator and empty strings are removed
     |      from the result.
     |  
     |  splitlines(...)
     |      S.splitlines(keepends=False) -> list of strings
     |      
     |      Return a list of the lines in S, breaking at line boundaries.
     |      Line breaks are not included in the resulting list unless keepends
     |      is given and true.
     |  
     |  startswith(...)
     |      S.startswith(prefix[, start[, end]]) -> bool
     |      
     |      Return True if S starts with the specified prefix, False otherwise.
     |      With optional start, test S beginning at that position.
     |      With optional end, stop comparing S at that position.
     |      prefix can also be a tuple of strings to try.
     |  
     |  strip(...)
     |      S.strip([chars]) -> string or unicode
     |      
     |      Return a copy of the string S with leading and trailing
     |      whitespace removed.
     |      If chars is given and not None, remove characters in chars instead.
     |      If chars is unicode, S will be converted to unicode before stripping
     |  
     |  swapcase(...)
     |      S.swapcase() -> string
     |      
     |      Return a copy of the string S with uppercase characters
     |      converted to lowercase and vice versa.
     |  
     |  title(...)
     |      S.title() -> string
     |      
     |      Return a titlecased version of S, i.e. words start with uppercase
     |      characters, all remaining cased characters have lowercase.
     |  
     |  translate(...)
     |      S.translate(table [,deletechars]) -> string
     |      
     |      Return a copy of the string S, where all characters occurring
     |      in the optional argument deletechars are removed, and the
     |      remaining characters have been mapped through the given
     |      translation table, which must be a string of length 256 or None.
     |      If the table argument is None, no translation is applied and
     |      the operation simply removes the characters in deletechars.
     |  
     |  upper(...)
     |      S.upper() -> string
     |      
     |      Return a copy of the string S converted to uppercase.
     |  
     |  zfill(...)
     |      S.zfill(width) -> string
     |      
     |      Pad a numeric string S with zeros on the left, to fill a field
     |      of the specified width.  The string S is never truncated.
     |  
     |  ----------------------------------------------------------------------
     |  Data and other attributes defined here:
     |  
     |  __new__ = <built-in method __new__ of type object>
     |      T.__new__(S, ...) -> a new object with type S, a subtype of T
    


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

Here is one more.  Just ask Google.  For example, look what happens when we ask Google about capitalization.

![](./ask-google.png)

[A great link with a detailed answer.](https://stackoverflow.com/a/1549644)

![](./stack-overflow.png)

Then we try this new method out ourselves, to see if this user on StackOverFlow is right (they normally are).


```python
"hello world".title()
```




    'Hello World'



And our work is done.

Feel free to look at [other common string operations here.](https://docs.python.org/2/library/string.html)

### Summary

In this lesson, we learned about our first datatype in Python: strings.  A string is just text.  We indicate to Python that we are writing a string by surrounding our content with quotation marks.  Once we do this, we can operate on this string by calling methods like `upper` or `endswith`.  We identified a general pattern for calling methods on datatypes: 'datatype-method name-dot-parentheses'.

The second thing we learned was different mechanisms for learning about methods.  We saw the importance of guessing and experimentation, and how doing so can give us error messages, which provide clues. We also saw how to ask questions about a datatype by calling 'help' followed by the datatype name like `help(str)`.  Finally, we saw we can ask Google.  This mechanism of exploration is a skill we'll build up over time and this course will provide guidance and practice on along the way.
