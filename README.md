# Demo for Inserting Images on README File

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
