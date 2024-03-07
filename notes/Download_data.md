### Download county level weather data

#### Source
https://www.osti.gov/biblio/1960548

#### instroduction

Detail

- Virtual env
https://www.osti.gov/biblio/1960548

- Actual download
https://data.msdlive.org/records/g4kct-fhy96


- **step one:** setting up virtual env

Windows
1.1 Open the command prompt.
1.2 Enter the following command:

```bash
python -m venv %HOMEPATH%\venvs\msdlive
```

Unix-based systems (Linux/macOS)
1.1 Open a terminal.
1.2 Enter the following command:

```bash
python3 -m venv ~/venvs/msdlive
```

- **step two:** Activating a Virtual Environment
Once you have created a virtual environment, you need to activate it in order to use it. The steps depend upon the operating system you are using:

Windows
2.1 Open the command prompt.
2.2 Enter the following command:

```bash
%HOMEPATH%\venvs\msdlive\Scripts\activate
```

Unix-based systems (Linux/macOS)
2.1 Open a terminal.
2.2 Enter the following command:

```bash
source ~/venvs/msdlive/bin/activate
```

After executing the appropriate command, you should see that the virtual environment is activated. The prompt in your command prompt or terminal will change to indicate that you are now working within the virtual environment. You can then install packages or run Python scripts within this activated venv.

- **step three:** Login
Once logged in, you will remain logged in until you log out or your token expires after 48 hours. If you are using a shared computer, we recommend logging out between sessions.

```bash
msdlive login
```

- **step four:** Download Files
Replace "MY_LOCAL_DIR" with the path to the directory where the files should be saved. * Note that g4kct-fhy96 is the unique ID for this dataset only.

```bash
msdlive download --dataset-id g4kct-fhy96 --output-dir MY_LOCAL_DIR
```

The following are optional

- **step five:**Log Out
```bash
msdlive logout
```

- **step six:**Deactivating a Virtual Environment
Once you have finished working in your virtual environment, you can deactivate it to restore your system's default Python environment:

Open a terminal (Linux/macOS) or command prompt (Windows)
Enter the following command:

```bash
deactivate
```

After executing the command, the virtual environment will be deactivated. The prompt will no longer display the venv name, indicating that you have returned to your system's default Python environment.