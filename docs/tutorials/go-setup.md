# Setting up a dev container for Go

* Primary author: [Rachel Alvis](https://github.com/rcalvis)

* Reviewer: [Mya Volety](https://github.com/mvolety)

Welcome! In this tutorial you will learn how to set up a dev container in Go. Using a dev container is important to ensure that your project will be runnable on any system.

## Prerequisites

You should have VSCode, Docker, and git installed on your system. Instructions are not included in this tutorial, but can be found in each's online documentations. You will not need to individually install Go as the dev container will handle this.

* [Download VSCode](https://code.visualstudio.com/download)
* [Download Docker](https://docs.docker.com/get-started/get-docker/)
* [Download git](https://git-scm.com/downloads)
* Make sure you have the "Dev Containers" extension for VSCode installed.

## Step 1: Dev Container Setup

!!! tip

    For the easiest setup, use VSCode's terminal to begin your project.

### 1. Create directory and initialize git

To begin, open VSCode and open a new terminal. 

!!! tip

    You can open a terminal in VSCode using the following keyboard shortcut: CTRL+Shift+`

Create a new directory by running the following command in the terminal:

``` bash
mkdir go-helloworld
```

Open your new directory in VSCode.

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

* `name`: Initializes a name for your dev container.
* `image`: Adds the image for Go from Microsoft.
* `extensions`: Installs Go for VSCode.

Save the file and commit to your git repo by following the same steps as before. Now, you will need to reopen your project in the dev container. To do so, open the command palette in VSCode with the following keyboard shortcut: CMD + Shift + P. Search for and click on "Dev Containers: Reopen in Container." 

Once you have reopened, your terminal should look different than before and should show the current working branch in parentheses. To ensure you have correctly set up your dev container, run the following command in your terminal:

``` bash
go version
```

Once you see a version of Go installed, you have now successfully created and opened a new dev container for Go!

## Step 2: Begin Your Go Project

### 1. Create Your Go Project

In your existing directory, create a new directory to hold the files for the Go Project. You can use the following commands in the terminal to create a subdirectory and mod file:

``` bash
mkdir go-project
cd go-project
go mod init go-project
```

By using the go mod command, you are creating a new module file. This will be "go.mod," which shows the dependencies of the program. This is standard practice when using Go, even if the project does not require any dependencies. Having an empty go.mod file makes it clear that the project does not use any dependencies.

### 2. Create Your .go File

To begin coding in Go, create a file in your directory titled "main.go". In this file you will need to include the following:

``` go
package main

import "fmt"

func main() {
    fmt.Println("Hello COMP423")
}
```

The headers are important for this file. Including `package main` indicates that this is an entrypoint to our program. Including `fmt` allows for printing to the standard output.

Once you have saved the file, you can run it with the following command in the terminal:

``` bash
go run main.go
```

You should see the output "Hello COMP423" in your terminal.

### 3. Compile your directory using `go build`

To compile your directory, use the following command in your terminal:

``` bash
go build
```

!!! note

    Make sure that you are in your directory you created for the Go project and not the overarching directory.

You will then be able to run your code using the following command in your terminal:

``` bash
./go-tutorial
```

This allows you to run the output without re-compiling. This helps with processing times and memory.

!!! note

    Make sure to commit any changes made. When working on project it is important to commit early and often!

Congratulations! You have successfully created a dev container and created your first Go project!
