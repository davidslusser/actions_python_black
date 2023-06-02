# actions_python_black
A Github action for code format checking with black.


<br/>

## How to use
In your .github/workflows directory, create a yaml file (such as main.yaml). Add a job for each desired workflow with the `uses` keyword. Use the `with` keyword to pass any desired variables.

Examples:

```
on: [push]

jobs:
  black:
    runs-on: ubuntu-latest
    name: "black"
    steps:
      - uses: davidslusser/actions_python_black@v1.0.0
```
<br/>

```
on: [push]

jobs:
  black:
    runs-on: ubuntu-latest
    name: "black"
    steps:
      - uses: davidslusser/actions_python_black@v1.0.0
        with:
          src: "src"
          options: "--check"
          pip_install_command: "pip install -e .[dev]"
          python_version: "3.9"
```


<br/>

## Inputs
  - **src:** source directory of code to check (defaults to "`.`")
  - **options:** optional flags/parameters used in black command (defaults to "`--check -v`")
  - **pip_install_command:** pip install command (defaults to "`pip install black`")
  - **python_version:** version of python to run workflow with (defaults to "`3.x`")


<br/>

## References
 - https://black.readthedocs.io/en/stable/
 - https://pypi.org/project/black/
