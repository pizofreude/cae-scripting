# CAE Scripting

This repo intended to centralize various scripting and automation processes in CAE tasks via Python, Macro, MATLAB/GNU Octave, VBA along with MS365 packages:

- Excel
- Word
- Outlook
- PPT
- Project
- Sharepoint


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

Now, the `(virtualEnvironmentName)` should be shown in the Terminal above the directory.

Once the venv activated, continue working like normal in local machine.

#### Deactivate the virtualEnvironmentName via the terminal:

```bash
deactivate
```

The output will be: Notice the `(virtualEnvironmentName)` is deactivated and not shown after the `deactive` command.


### Install libraries

#### Show Installed Libraries

```bash
pip freeze
```

For a newly setup venv, nothing should be returned as it just freshly built.

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


## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

This project is licensed under an [MIT license](https://github.com/pizofreude/py.ms365/blob/main/LICENSE).






