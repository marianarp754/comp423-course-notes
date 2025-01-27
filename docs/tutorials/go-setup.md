# Setting up a Dev Container for Go

* Primary author: [Mariana Rodriguez-Pacheco](http://github.com/marianarp754)
* Reviewer: [Ashley Pearson](https://github.com/uncapearso2)

1. **Prerequisites**
    - Install Git, Visual Studio Code (VSCode), and Docker.
    - Create a GitHub account.
    - Ensure the `Dev Containers` VSCode plugin is installed.
    - Ensure the `Go` VSCode Plugin (Made by the Go Team at Google) is installed.


2. **Instructions for initializing a new Git repository**
    - In your terminal, create a new directory called `go-tutorial` and initialize a new Git repository:
        ```
        mkdir go-tutorial
        cd go-tutorial
        git init
        ```
    - Create a `README.md` file in your `go-tutorial` directory and commit its changes. 
        ```
        echo "# COMP_423_Go_Hello_World" > README.md
        git add README.md
        git commit -m "Initial commit with README"
        ```
    - Now, navigate to your browser and log into your GitHub account. 
    - Create a new repository with the following details:
        - Name: comp423-go-hello-world
        - Description: "Getting started with Go."
        - Visibility: Public
        - Leave the `Add a README file` unchecked.
    - Navigate back to your terminal and add your GitHub `comp423-go-hello-world` repository as a remote repository. 
        ```
        git remote add origin https://github.com/<username>/comp423-go-hello-world.git
        ```
    !!! note Note
        Check that your default branch is named `main` by typing `git branch` into the terminal. If it is not, rename it using `git branch -M main`.
    - Push your local commits to GitHub:
        ```
        git push -u origin main
        ```


3. **Instructions for Creating a New Dev Container Project for Go**   
    - In your terminal, create a `.devcontainer` directory in your `go-tutorial` directory.
        ```
        mkdir .devcontainer
        ```    
    - Navigate to VSCode and open your `go-tutorial` directory.
    - Create a `devcontainer.json` file in your `.devcontainer` directory and use a Microsoft Go Dev Container base image.
        ```
        {
            "name": "Go Dev Container",
            "image": "mcr.microsoft.com/devcontainers/go:0-1",
            "customizations": {
                "vscode": {
                    "extensions": ["golang.go"]
                }
            }
        }
        ```
    - Open the Command Palette (Control+Shift+P) and run Dev Containers: Reopen in Container.
    !!! note Note
        To check if you have successfully reopened your project in a Dev Container, open a terminal in VSCode and run `go version` to check that your dev container is running a recent version of Go. 


4. **Dev Container Configuration File Explanations**
    - The devcontainer.json file configures your development environment. In this example:
        - name: provides a descriptive name for your dev container
        - image: specifies the Docker image to use
        - customizations: configures VS Code by adding useful extensions 


5. **Create and Run a "Hello COMP423" Program**
    - In VSCode, create a `main.go` file in your `go-tutorial` directory that includes:
        ```
        package main
    
        import "fmt"
        func main() {
            fmt.Println("Hello COMP423")
        }
        ```
    - In your terminal in VSCode, run Go:
        ```
        go run main.go
        ```
    - Then, build the Program:
        ```
        go build main.go
        ./main
        ```
    !!! note Note
        The `go build` command compiles Go code into a standalone binary executable, similar to how `gcc` compiles C code in COMP211. This binary can run independently, making it ideal for production use. On the other hand, `go run` compiles and executes the code in one step without creating a reusable binary, making it more convenient for quick testing and development. 


6. **The Program's Requirement is that it Prints "Hello COMP423" Out to Standard Output**
    - The program should output the text `"Hello COMP423"` to the terminal when executed.
    - Once your program executes successfully, push your finished product to GitHub. 
        ```
        git add .
        git commit -m "My first Go Hello World Program"
        git push -u origin main
        ```