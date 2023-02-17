# py.ms365

Python repo for coding with MS365 packages:

- Excel
- Word
- Outlook
- PPT
- Project


## Library 

pip install openpyxl

## Python Virtual Environment

Best practice before creating python project to avoid dependencies error across programs is to code in virtual environment.

### Setup

Go to desired directory in the terminal, then type in command line:

Windows:

```bash
python -m venv virtualEnvironmentName
```
p/s: Shorter name is better like venv or virt.

Mac: 

```bash
python3 -m venv virtualEnvironmentName
```
A directory of `virtualEnvironmentName/` should be made in the selected path.

#### Activate the virtualEnvironmentName via the terminal:

```bash
source virtualEnvironmentName/Scripts/activate
```

Now, the `(virtualEnvironmentName)` should be shown in the Terminal above the directory:

![venv](https://user-images.githubusercontent.com/108355948/219313517-ddd0c7d1-cf1d-4749-bcdf-9e4d55f79ceb.png)

Once the venv activated, continue working like normal in local machine.

#### Deactivate the virtualEnvironmentName via the terminal:

```bash
deactivate
```

The output will be: Notice the `(virtualEnvironmentName)` is deactivated and not shown after the `deactive` command.

![venv2](https://user-images.githubusercontent.com/108355948/219314010-b1d9a717-e976-4cd2-95e5-2e0614e03a25.png)

### Install libraries

#### Show Installed Libraries

```bash
pip freeze
```

For a newly setup venv, nothing should be returned as it just freshly built.

After installing via `pip install <libraryName>`, the output should be e.g.:

![venv3](https://user-images.githubusercontent.com/108355948/219328637-301314f8-cced-496e-b4e6-b240a07aa1cb.png)

### Creation of requirements.txt

At the end of the project, do this:

- Windows:

```bash
pip freeze > requirements.txt
```

- Mac/Linux:

```bash
pip3 freeze > requirements.txt
```

So that, other user can simple recreate the venv via:

- Windows:

```bash
pip install -r requirements.txt
```

- Max/Linux:

```bash
pip3 install -r requirements.txt
```









