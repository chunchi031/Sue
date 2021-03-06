Sue
===

Pseudocode-to-Python translator


  Hello! Welcome to Sue, the pseudocode-to-Python translator. The goal of this project is to create a wrapper around Python that allows the use of natural language inputs to produce working Python programs.

  At this time, there is very little functionality in Sue. What works is a limited For-loop construction, a print function, a variable declaration function, and a tabbing function. Stay tuned for more features.
  
  

Implementation:

All commands that you would like Sue to translate into Python must first be put into commandInput.txt. An example set of Sue code is currently in commandInput.txt.



Syntax:



For-Loops:

To create a For-loop, your command should be based on this syntax:

iterate [iterator] over a range between [range beginning] and [range ending].

The iterator can be any single string, and the beginning and end of the range can be any integers. The syntax for this is not strict. All Sue commands are split into lists for parsing, so, in this case, the only thing to keep in mind is what index the keyword "iterate", the iterator, and the range bounds will eventually be at in the list. Described with the aid of some Pythonesque code:

The keyword "iterate" must be at list[0]

The iterator must be at list[1]

The range beginning must be at list[-3]

The range ending must be at list[-1]

This means that it is possible to provide input to Sue that looks like this:

iterate i range 0 to 100

The split of that would look something like this:

['iterate', 'i', 'range', '0', 'to', '100']

Notice that all required information is in the appropriate indices.

NOTE: no keywords that are implemented in Sue are case-sensitive. "iterate" and "Iterate" are treated and understood equally by Sue.


Printing:

There's not much more to printing in Sue than there is in Python. The syntax is as follows:

print [string]

[string] need not be quoted.

The function that takes care of printing could use work. Further descriptions of what's wrong with this Sue feature are further described in sue.py.

Variable Declaration:

Syntax:

declare variable [variableName] as a [data type]

An example of this would be: declare variable num as an integer.

Again, as long as the parsed input has the right keywords at the rigth places, then Sue will execute the command correctly.

Start the declaration statement with keyword "declare" (again, not case-sensitive) and then have the variable name at lst[2] and have the variable data type at lst[-1].

Potential input for the declaration statement: declare var num integer

Tabbing:

Tabbing is the way that scope is shown in Python, so there has to be a way for Sue to make tabs if the resulting Python program is to function. All that you need to do to add a tab in the final Python program is to add a line in your input that is only a left bracket ("{"). This will be parsed by Sue and will result in a tab wherever you need to delineate scope (if you look at the code for the tabbing function, then you'll see that the function acounts for the number of tabs needed as well.) In order to take yourself out of the current scope, use "}". Make sure the number of left and right brackes match so that you don't have issues with scope.


Commenting:

  Commenting at this point in Sue's life is very free-form. In the same way that a right bracket will simply be ignored by Sue, any line of text in commandInput.txt that does not begin with one of the currently recognized keywords will be ignored. At this point, to make things easier, I would recommend that you follow Python's commentig syntax and use a "#" before your comment. This will be ignored by Sue (given that "#" is not a keyword) and will also serve as aid for the user.



These functions are all that Sue can do at this time. This readme will grow over time, so come again and see what's new! If you'd like to help, do so at your leisure.



Thanks for your time!



















































