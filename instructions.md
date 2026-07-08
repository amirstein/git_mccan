# Git + dbt + Snowflake Setup Instructions

## Git clone 
1. C -> Users -> User -> documents -> open new folder, name: git_mccann_instructions
2. Open vs code
3. Open folder -> go to *git_mccann_instructions yellow folder* -> open folder
4. Open a new terminal

run:
``` 
https://github.com/<personal_account>/git_mccan.git
cd git_mccan
```

## 1. Check dbt

```powershell
dbt --version
where.exe dbt
```

## 2. Check Python

```powershell
python --version
where.exe python
```

## 3. Create a virtual environment

```powershell
py -m venv venv
.\venv\Scripts\activate
```

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

**Check:**

```powershell
where.exe python
```

## 4. Install dbt-snowflake

Release page: https://github.com/dbt-labs/dbt-snowflake/releases

```powershell
pip install dbt-snowflake(==1.7.4)
```

If the venv causes issues, run on bash:
> ```powershell
> .\.venv\Scripts\python.exe -m pip install dbt-snowflake==1.7.4
> ```

**Check** :

```powershell
->-> site-packages getting full
where.exe dbt
where.exe python
```

## 5. GitHub setup

1. Create a new repository on your personal GitHub account.
2. C -> Users -> User -> documents -> open new folder, name: mccann_personal_repo
3. Open vs code , open folder (C documents), new terminal
4. Clone the repo:

   ```powershell
   git clone <repository_url>
   cd <repository_name>
   git status
   ```

## 6. Initialize a dbt project

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

## 7. Branch, change, and PR

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

## 8. Run dbt

```powershell
cd <dbt_project>
dbt debug
```

## 9. If you have time

*(TBD)*
