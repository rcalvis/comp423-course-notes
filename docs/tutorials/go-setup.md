# Setting up a dev container for Go

* Primary author: [Rachel Alvis](https://github.com/rcalvis)

* Reviewer: [Mya Volety](https://github.com/mvolety)

Insert instructions here. Testing code block below.

## Using Code Blocks in Mkdocs

Code blocks are useful for including lines of code in your site. For example, the following code blocks shows a simple Python function.

``` py
def sum(x,y):
    return x + y
```

To use code blocks, use three backticks (`) as the starting and ending markers for your code. Specify the language in the first line. An example is provided below which would produce the code block identified above.

``` md title="Code Block"
 ``` py
 def sum(x, y):
     return x + y
 ```
```

To include titles for your code blocks, include 'title="<name>"' in the same line that the language was specified in.

``` md title="Code Block with Title"
 ``` py title="sum.py"
  def sum(x, y):
     return x + y
 ```
```

## Using Admonitions in Mkdocs
