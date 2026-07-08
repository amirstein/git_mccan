# Git + dbt + Snowflake Setup Instructions

## Git clone 
1. C -> Users -> User -> documents -> open new folder, name: git_mccann_instructions
2. Open vs code
3. Open folder -> go to *git_mccann_instructions yellow folder* -> open folder
4. Open a new terminal

run:
``` 
git clone https://github.com/amirstein/git_mccan.git
cd git_mccan
```

### Initial validation:
#### We want to see if dbt already exists (installed) in the computer
dbt:

```powershell
dbt --version
where.exe dbt
```
python:

```powershell
python --version
where.exe python
```

## Create a virtual environment

```powershell
py -m venv venv
.\venv\Scripts\activate
```
### Validation:
- Powershell display: green brackets, left side of terminal path (i.e (venv)c:/users/user)
- Bash display: white brackets, above path (i.e (venv))

**If you have any issues:** 

open bash: 
```
cd git_mccan and run: source venv/Scripts/activate
```


else

power shell (kind of force):
```
$env:VIRTUAL_ENV = "C:\Users\User\Documents\<folder_name>\git_mccan\venv"
$env:PATH = "$env:VIRTUAL_ENV\Scripts;" + $env:PATH
```

**Validation:**

```powershell
where.exe python
```

## Install dbt-snowflake

Release page: https://github.com/dbt-labs/dbt-snowflake/releases

For specific version:

```powershell
pip install dbt-snowflake==1.7.4
```
For most updated version:
```powershell
pip install dbt-snowflake
```

If the venv causes issues, run on bash:
> ```powershell
> .\.venv\Scripts\python.exe -m pip install dbt-snowflake==1.7.4
> ```

**Validation** :

```powershell
->-> site-packages getting full
where.exe dbt
where.exe python
```

## GitHub setup

1. Create a new repository on your personal GitHub account.
2. C -> Users -> User -> documents -> open new folder, name: mccann_personal_repo
3. Open vs code , open folder (C documents), new terminal
4. Clone the repo:

   ```powershell
   git clone <repository_url>
   cd <repository_name>
   git status
   ```

## Initialize a dbt project
**FYI- There may be issues with local user details and Github account**

In Git Bash :

```bash
dbt init new_project
git add new_project
git commit -m "initial commit"
git push
```
If dbt init new_project not execute as expected check if python version cause the issue 
( pip install dbt-snowflake --upgrade ) or ask AI
Somwtimes there is a conflict between python version and dbt packages

**Check:** confirm the push on GitHub.

## Branch, change, and PR

Still in Git Bash:

```bash
git switch -c new_branch
# <make a change to the file>
git status
git add <file>
git commit -m "<message>"
git push
```

Then on GitHub:

1. Open a new pull request.
2. Merge the PR.

**Check:** back in PowerShell:

```powershell
where.exe dbt
```

## Run dbt

```powershell
cd <dbt_project>
dbt debug
```

## 9. If you have time
1. Ask soneone to clone your repo
2. Let the other employee change something in one of the docs
3. he will push the change
4. You also make a change and push it without pull
5. THe purpose is to deal with conflict and solve it
