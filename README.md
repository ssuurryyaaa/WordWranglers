# How to work on this project?

## <u>Cloning the project</u>
The project can be either downloaded as a zip file from the git repository [WordWranglers](https://github.com/ThusharaN/WordWranglers) or cloned using the following git command:
```sh
git clone https://github.com/ThusharaN/WordWranglers.git
```
The project can then be opened in Visual Studio Code or any other IDE.

## <u>Setting up the project</u>
<b>Poetry</b> is used as a package management and dependency resolution tool to simplify the management of dependencies in this project. Make sure both poetry and pre-commit packages are installed before following the set-up instructions.
```sh
pip install poetry
pip install pre-commit
```
Follow the below steps to create an initial setup for the project:

Configuring poetry to make an env in the project

```sh
poetry config virtualenvs.in-project true
```

Create a new vitual environment using poetry

```sh
poetry install
```

Activating the environment

```sh
poetry shell
```

Install dependencies

```sh
pip install -r requirements.txt
```

Now install the precommit hooks by running this in the activated environment

```sh
pre-commit install
```

Select the interpreter with path <b>./.venv/bin/python</b> in VSCode.
<br>![Alt text](/interpreter.png?raw=true "Title").

Do a test run (after installing matplotlib) to check if the environment has been setup correctly

```sh
python3 app/src/test_run.py
```
<br>

>**Note:** Instructions for installing git can be found [here](https://git-scm.com/downloads). Most Mac/Linux machines will have git pre-installed.

## <u>Adding Dependencies</u>
Dependencies can added to the current virtual environemt by running the following command
```sh
pip install <package_name> && pip freeze > requirements.txt
```
<br>

>**Note:** Make sure you are insidethe virtual environment created by poetry before installing any dependencies

## <u>Making changes</u>
A pull request needs to be created in order to push any changes to code.

After cloning, create a local branch to work on.

```sh
git checkout master
git checkout -b <your_branch_name>
```

In case a change has been made to <b>hello.py</b>, run the following commands to commit the changes

```sh
git status // Gives the paths of the files that have been updated
git add <file_path>/hello.py
git commit -m <some_commit_message>
```
In case new packages were installed, add the updated <b>requirements.txt</b> to the commit. Push your branch to GitHub

```sh
git push origin <your_branch_name>
```

Raise a pull request through GitHub. If the request shows conflicts, run the following commands locally

```sh
git fetch origin
git rebase origin/master
```
Fix all the conflicts in the files; add, commit and push.
<br>

>**Note:** More git commands can be found [here](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)

## <u>Running the program</u>

Run the following command in the console to train the model:
```sh
python3 question_classifier.py --train --config [configuration_file_path]
```

and the following command to test the model:
```sh
python3 question_classifier.py --test --config [configuration_file_path]
```

Once training and testing of the model is complete, the environment can be deactivated by running the followig command in the terminal
```sh
source deactivate
```
