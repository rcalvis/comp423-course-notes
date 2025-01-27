# Setting up a dev container for Go

* Primary author: [Rachel Alvis](https://github.com/rcalvis)

* Reviewer: [Mya Volety](https://github.com/mvolety)

Welcome! In this tutorial you will learn how to set up a dev container in Go. You will also learn how to start your own website using Material for Mkdocs. Material for Mkdocs is a very useful way to easily make websites without the heavy lifting of HTML and CSS.

## Prerequisites

You should have VSCode, Docker, and git installed on your system. Instructions are not included in this tutorial, but can be found in each's online documentations. You will not need to individually install Go as the dev container will handle this.

* [Download VSCode](https://code.visualstudio.com/download)
* [Download Docker](https://docs.docker.com/get-started/get-docker/)
* [Download git](https://git-scm.com/downloads)

## Step 1: Dev Container Setup

### 1. Create directory and initialize git

To begin, open VSCode and open a new terminal. Create a new directory by running the following command in the terminal:

``` bash
mkdir <directory name>
cd <directory name>
```

To initialize a new git repository, ensure you have git installed correctly and run the following command inside of the directory you created:

``` bash
git init
```

You have now successfully created a new directory and git repository. You can now begin adding commits!

### 2. Create your first commit

Every project should include a README.md file. Create a new file in your directory titled "README.md" with the following contents:

``` md
# Dev Container for Go
```

Save the file in VSCode (CMD + S). Then open a new terminal and save/commit the changes to git using the following commands:

``` bash
git add .
git commit -m "<Add a meaning commit message here>"
```

This will ensure that your changes are added to your local git repository.

### 3. Create dev container

While inside of your project's directory, create a new directory for the dev container's setup using the following command in the terminal:

``` bash
mkdir .devcontainer
```

Inside of the .devcontainer directory, create a JSON file titled "devcontatiner.json". Inside the file, include the following contents:

``` json
{
    "name": "Go Dev Container",
    "image": "mcr.microsoft.com/devcontainers/go",
    "customizations": {
        "vscode": {
            "extensions": ["ms-vscode.go"]
        }
    }
}
```

Save the file and commit to your git repo by following the same steps as before. Now, you will need to reopen your project in the dev container. To do so, open the command palette in VSCode with the following keyboard shortcut: CMD + Shift + P. Search for and click on "Dev Containers: Reopen in Container." 

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
