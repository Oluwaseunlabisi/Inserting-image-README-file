# Demo for Inserting Images on README File
Imagine this simple deployment flow:

* A developer pushes code to GitHub
* GitHub Actions builds a Docker image
* Docker deploys the app to a Linux VM
* Nginx serves the application

1. Creating Screenshots directory 
```bash
mkdir screenshots
```
![creation of screenshot directory](screenshots/image-directory-creation.png)

2. Creating a README File  
```bash
touch README.md
```    
![creation of README File](screenshots/readme.md-file-creation.png)

3. Github Repo Authentication
```bash
gh auth login
```
![Github Repo Authentication](screenshots/git-login.png)

4. Github Repo Update
```bash
git init
git add .
git commit -m "Updating README File"
git branch -M main
gh repo create Inserting-image-README-file --public --source=. --remote=origin --push
git remote -v
```

5. Downloading, Installing and Verifying Graphviz Installation

Install:

```bash
winget install Graphviz.Graphviz
```
![Graphviz Install](screenshots/graphviz-installation.png)

Verify:

```bash
dot -V
```
![Graphviz Install Verification](screenshots/graphviz-installation-verification.png)


6. Creating Architecture Diagram

Open:

```bash
nano docs/architecture.dot
```

Paste:

```dot
digraph Architecture {

    rankdir=LR;

    node [shape=box style=filled fillcolor=lightblue];

    User -> GitHub;
    GitHub -> "GitHub Actions";
    "GitHub Actions" -> Docker;
    Docker -> AzureVM;
    AzureVM -> Nginx;
    Nginx -> Application;
}
```
![Diagram Source Codes](screenshots/diagram-source-codes.png)

Generate architecture image:

```bash
dot -Tpng docs/architecture.dot -o docs/architecture-diagram.png
```

Open image:

```bash
open docs/architecture-diagram.png
```
![Architecture Diagram](docs/architecture-diagram.png)