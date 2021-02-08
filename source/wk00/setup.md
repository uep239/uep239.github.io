# Configuring the Course Environment

The following will walk you thorough configuring your **personal Windows or macOS** computer into a comfortable geospatial programming environment. Note that detailed instructions are not provided for **Linux** users as we assume you know that you are doing. Please contact the course staff if you do not have access to a suitable computer **on which you have administrative privileges** or if you need additional assistance with the setup. (Linux users are also welcome to reach out.)

In addition to configuring certain system settings, we will be installing the following software:

- [**Thonny**](https://thonny.org/) – a beginner-friendly integrated development environment (IDE) for Python
- [**Google Chrome**](https://www.google.com/chrome/) or [**Mozilla Firefox**](https://www.mozilla.org/en-US/firefox/new/) – required to run [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) without any issues
- [**Visual Studio Code**](https://code.visualstudio.com/) (also known as VS Code) – a powerful code-friendly text editor with many useful features
- [**Git**](https://git-scm.com/) – the most widely used distributed version control software
- [**Miniconda**](https://docs.conda.io/en/latest/miniconda.html) – a lightweight Python distribution that comes bundled with the [Conda](https://docs.conda.io/en/latest/) package manager
- [**Windows Terminal**](https://docs.microsoft.com/en-us/windows/terminal/) and [**PowerShell Core**](https://docs.microsoft.com/en-us/powershell/) – the next-generation command-line interface for Windows

If you already happen to have any of the aforementioned software installed and configured, please carefully review the instructions below to see what configuration is recommended for this course. All course materials after this point assume the following configuration and if yours differs, you want to make sure you are aware of the differences and are able to circumnavigate any potential issues that might result. Also note the following:

- If you have worked with code before and already have a favorite Python-friendly text editor and/or IDE installed, feel free to skip the Thonny and/or Visual Studio Code installation and use your preferred application(s) instead.
- If you are an experienced Conda user with a preexisting Anaconda/Miniconda installation, there is no need to change your current configuration at this time. Just make sure you have `jupyterlab>=3` installed, as we will be using it soon.
- If you are not too comfortable with the Conda package manager, it is highly recommended that you completely uninstall any preexisting Anaconda or Miniconda installations and start over with a clean sheet.
- It goes without saying, but the Windows Terminal and PowerShell Core section applies to Windows users only.

Please perform all installations and configuration changes in the order they are listed, as subsequent steps rely on all previous ones. Toggle the tab corresponding to your operating system to view the appropriate instructions.

```{note}
Instead of manually typing the commands in the instructions into Terminal or PowerShell, you can just copy and paste the command, and then press **Enter/Return** to run it. You can easily copy a whole command block by clicking the copy icon in the upper-right corner of the block.
```
```{attention}
When copying and pasting multiline command blocks into Terminal or PowerShell, all commands (lines) but the last will automatically run one after another. However, to execute the last command, you **must press Enter/Return once all previous commands have finished!**
```

## Configure System Preferences

Both the Windows and macOS operating systems are configured for the average user by default, with many useful advanced features either disabled or hidden. The average users does not care for these features, but for us, they are extremely useful and perhaps even vital. Please follow the instructions below to show hidden files and filename extensions, and allow the installation and execution of various third-party applications and scripts.

```{danger}
The following will make your system more vulnerable to malicious scripts and applications. Only install applications and execute scripts that you received from a trustworthy source. **Do not execute scripts you do not understand!**
```

````{tabbed} Windows
**Show hidden files and filename extensions:**

1. Open **File Explorer**.
2. Select the **View** tab.
3. In the *Show/Hide* section, ensure the following boxes are **checked**:
    - ***File name extensions***
    - ***Hidden items***

**Set Windows PowerShell as your default shell:**

1. *Right-click* on your taskbar and click on **Taskbar settings**.
2. Ensure *Replace Command Prompt with Windows Powershell in the menu when...* is toggled **ON**.

**Allow the execution of third-party scripts:**

1. *Right-click* on the **Start** button and select **Windows PowerShell (Admin)**.
2. Click **yes** when asked for confirmation, enter an **administrator** password if needed.
3. Run the following command *(either type or copy and paste, then press __Enter__ to run)*:
    ```powershell
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine -Force
    ```
````
````{tabbed} macOS
**Show filename extensions and configure Finder:**

1. Open **Finder** and ensure that *View > Show Path Bar* is **checked**.
2. Then go to *Finder > Preferences...*
2. In the *General* section, ensure all items under ***Show these items on the desktop*** are **checked**.
3. In the *Advanced* section, ensure ***Show all filename extensions*** is **checked**.

**Show hidden files:**

1. Open **Terminal** from *Applications*.
2. Run the following command *(either type or copy and paste, then press __Return__ to run)*:
    ```bash
    defaults write com.apple.finder AppleShowAllFiles YES
    ```

**Allow the installation of third-party applications:**

1. Open **Terminal** from *Applications*.
2. Run the following command *(either type or copy and paste, then press __Return__ to run)*:
    ```bash
    sudo spctl --master-disable
    ```
3. When prompted, enter your **administrator** password.
4. Go to *System Preferences > Security and Privacy*.
4. Click the ***padlock*** in the bottom, enter your **administrator** password again if needed.
5. Near the bottom of the *General* tab, select **Anywhere** under ***Allow apps downloaded from***.
````


## Install Thonny and a Suitable Web Browser

**Thonny** is a beginner-friendly integrated development environment (IDE) for Python that is actually written in Python and comes bundled with its own self-contained Python environment. To install Thonny on your computer, download a suitable installer from [**thonny.org**](https://thonny.org/) and accept all default settings.

If you do not already primarily use the [**Google Chrome**](https://www.google.com/chrome/) or [**Mozilla Firefox**](https://www.mozilla.org/en-US/firefox/new/) web browser, you should install one of them and set it as your default browser. Other browsers like Edge or Safari might not be compatible with the [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) interactive notebook interface or the interactive sections of the course website.


## Install Visual Studio Code

Visual Studio Code (VS Code) is a powerful open-source text editor that works well with both Python and Markdown, and is well suited for our purposes. It is cross-platform and has numerous extremely useful features, making it a robust coding environment for all operating systems. However, its functionality is unmatched on the Windows platform, making it a must-have for aspiring developers who also happen to be Windows users.

```{tabbed} Windows
1. Download a suitable Visual Studio Code installer: <https://code.visualstudio.com/download>
2. Run the downloaded installer and accept the default settings **until you reach _Select Additional Tasks_**.
3. In the *Select Additional Tasks* window, ensure the following options are **selected**:
    - Add *Open with Code* action to Windows Explorer file context menu
    - Add *Open with Code* action to Windows Explorer directory context menu
    - **Register Code as an editor for supported file types**
    - **Add to PATH (requires shell restart)** *(this should be selected by default, __do not unselect__)*
4. Click **Next** and then **Install** to confirm the installation.
```
```{tabbed} macOS
1. Download a suitable Visual Studio Code installer: <https://code.visualstudio.com/download>
2. Locate the downloaded archive and select the *magnifying glass* icon to open it in **Finder**.
3. Drag **Visual Studio Code.app** into the *Applications* folder.
4. *Right-click* on Visual Studio Code icon and select ***Options > Keep in Dock***.
5. Launch Visual Studio Code.
6. Open the **Command Palette** via *View > Command Palette* or by pressing **Ctrl+Shift+P**.
7. Type ***shell command*** into the Command Palette.
8. Select **Shell Command: Install 'code' command in PATH**.
```


## Install and Configure Git

Git is the most popular distributed version control software, originally developed by [Linus Trovalds](https://en.wikipedia.org/wiki/Linus_Torvalds) – the same [Finn](https://en.wikipedia.org/wiki/Finland) who created the Linux operating system (which pretty much runs half of the world). The following will guide you thorough installing Git on your computer and configuring it to be more convenient for you to use throughout the semester.

```{attention}
You will need to create GitHub account before proceeding (unless you already have one): **<https://github.com/join>**
```

### Install and Git and Configure Basic Settings

````{tabbed} Windows
**Install Git for Windows:**

1. Download the latest **Git for Windows** installer: <https://git-scm.com/download/win>
2. Run the downloaded installer and accept the default settings **until you reach _Choosing the default editor used by Git_**.
3. In the *Choosing the default editor used by Git* window, select **Use Visual Studio Code as Git's default editor**.
    - If have another text editor you use, feel free to select that one instead of Visual Studio Code.
    - Select ***Use Notepad as Git's default editor*** if your preference is not listed.
4. Click *Next* and select **Override the default branch name for new repositories** and keep ***main*** as the default name.
5. Click *Next* and ensure **Git from the command line and also from 3-rd party software** is selected *(should be the default)*.
6. Click *Next* and accept the default selection **Use the OpenSSL library**.
7. Click *Next* and ensure **Checkout Windows-style, commit Unix-style line endings** is selected *(should be the default)*.
8. Click *Next* and accept the default selection **Use MinTTY (the default terminal of MSYS2)**.
9. Click *Next* and ensure **Default (fast-forward or merge)** is selected *(this should be the default selection)*.
10. Click *Next* and accept the default selection **Git Credential Manager Core**.
11. Keep clicking though the installer and accepting the default settings until the installation has completed.

**Configure Git:**

1. *Right-click* on the **Start** button and select **Windows PowerShell**.
2. Run the following command, replacing the example name with your own name (wrap it in quotes as in the example):
    ```powershell
    git config --global user.name "Susie Student"
    ```
3. Run the following command, replacing the example email with the email address linked to your GitHub account:
    ```powershell
    git config --global user.email susie.student@example.com
    ```

````
````{tabbed} macOS
**Install Git or confirm your installation:**

1. Open **Terminal** from *Applications* and run the following command:
    ```bash
    git --version
    ```
- If an installer launches, walk through the installer and accept all default settings.
- If a version number is returned instead and no installer launches, you have Git installed.

**Configure Git:**

1. Close any open **Terminal** windows and open a new **Terminal** window from *Applications*.
2. Run the following command, replacing the example name with your own name (wrap it in quotes as in the example):
    ```bash
    git config --global user.name "Susie Student"
    ```
3. Run the following command, replacing the example email with the email address linked to your GitHub account:
    ```bash
    git config --global user.email susie.student@example.com
    ```
4. Run the following command:
    ```bash
    git config --global init.defaultBranch main
    ```
5. Configure the text editor Git uses by default as follows:
    - If you installed **Visual Studio Code**, run the following:
        ```bash
        git config --global core.editor "code --wait"
        ```
    - If you would like to use a different text editor, refer to the [Git documentation](https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Setup-and-Config#ch_core_editor) for the appropriate command.
    - If you are unable to find a suitable command for your preference, default to **nano** as follows:
        ```bash
        git config --global core.editor "nano -w"
        ```
````

### Configure an SSH Key for GitHub Authentication

Setting up an SSH (Secure Shell) key and linking it to your GitHub account will allow you to use the `git` command to access your GitHub account directly without having to manually type in your password and username every time.

```{warning}
This will allow anyone with access to your computer (or local user account) also access your GitHub account.
```
```{note}
If you know that you already have a public-private SSH key pair that you would like to use for GitHub, feel free to skip the section on generating an SSH key. Any preexisting SSH keys would be located in the `~/.ssh` directory.
```

```{tabbed} Windows
**Create a new SSH key to use with GitHub:**

1. *Right-click* on the **Start** button and select **Windows PowerShell**.
2. Run the following command, replacing the example email with the email address linked to your GitHub account:
    ```powershell
    ssh-keygen -t ed25519 -C "susie.student@example.com"
    ```
3. When prompted to *enter a file in which to save the key*, press **Enter** to accept the default location.
    - *Make note of the filename if it differs from the default filename of `id_ed25519`.*
4. When prompted to *enter passphrase*, leave it empty and press **Enter** twice to confirm.

**Link a new SSH key to your GitHub account:**

1. If you do not already have **Windows PowerShell** open, *Right-click* on the **Start** button and select *Windows PowerShell*.
2. Copy the newly generated (or any other desired) SSH **public** key to your clipboard *(modify the filename if needed)*:
    ```powershell
    Get-Content (Resolve-Path ~\.ssh\id_ed25519.pub) | clip
    ```
3. Go to **<https://github.com/settings/keys>** and log in with your GitHub account if needed.
4. Click on **New SSH key**.
5. The **Title** field should contain a descriptive label that will allow you to identify this key later. (As the key is linked to your computer, the name or description of the computer would be a good choice, for example *ThinkPad X1* or similar.)
6. Paste the copied **public** key into the **Key** field.
7. Click on **Add SSH key**.
8. If prompted, confirm your GitHub password.
```
```{tabbed} macOS
**Create a new SSH key to use with GitHub:**

1. Launch **Terminal** from *Applications*.
2. Run the following command, replacing the example email with the email address linked to your GitHub account:
    ```bash
    ssh-keygen -t ed25519 -C "susie.student@example.com"
    ```
3. When prompted to *enter a file in which to save the key*, press **Return** to accept the default location.
    - *Make note of the filename if it differs from the default filename of `id_ed25519`.*
4. When prompted to *enter passphrase*, leave it empty and press **Return** twice to confirm.

**Link a new SSH key to your GitHub account:**

1. If not already open, launch **Terminal** from *Applications*.
2. Copy the newly generated (or any other desired) SSH **public** key to your clipboard *(modify the filename if needed)*
    ```bash
    pbcopy < ~/.ssh/id_ed25519.pub
    ```
3. Go to **<https://github.com/settings/keys>** and log in with your GitHub account if needed.
4. Click on **New SSH key**.
5. The **Title** field should contain a descriptive label that will allow you to identify this key later. (As the key is linked to your computer, the name or description of the computer would be a good choice, for example *MacBook Air* or similar.)
6. Paste the copied **public** key into the **Key** field.
7. Click on **Add SSH key**.
8. If prompted, confirm your GitHub password.
```

### Install the GitHub CLI (Optional)

The GitHub command-line interface (CLI) allows you to work with your GitHub repositories without having to type out long commands and gives you access to additional GitHub functionality not possible with the traditional `git` tool. Once you are more comfortable with Git and GitHub, it will simplify various workflows and make your life easier. However, right now you might not see much value in installing it, so feel free to [**skip**](#install-and-configure-miniconda) this part.

````{tabbed} Windows
1. Navigate to: <https://github.com/cli/cli/releases/latest>
2. Scroll down to **Assets** and download the **MSI** installer.
    - *The filename should be similar to `gh_X.X.X_windows_amd64.msi` with `X.X.X` replaced with the latest version number.*
3. Run the downloaded installer and accept all default settings.
4. *Right-click* on the **Start** button and select **Windows PowerShell**.
5. Configure the GitHub CLI by running the following command:
    ```powershell
    gh auth login
    ```
6. Select **GitHub.com** and **Login with a web browser**, then follow all subsequent instructions.
````
`````{tabbed} macOS
You will need either [**Homebrew**](https://brew.sh/) or [**MacPorts**](https://www.macports.org/) to install the GitHub CLI. If you do not already have either of those set up, it is recommended you [**skip**](#install-and-configure-miniconda) this section instead of trying to set up another package manager. We do not really need the GitHub CLI and it is not worth the hassle.

```{caution}
If you already have Anaconda or Miniconda installed, you should always deactivate all active Conda environments using `conda deactivate` before installing anything using a different package manager like Homebrew or MacPorts.
```

````{tabbed} Homebrew
1. Launch **Terminal** from *Applications*.
2. Install the GitHub CLI by running the following commands:
    ```bash
    brew install gh
    ```
2. Run the following command to configure the GitHub CLI:
    ```bash
    gh auth login
    ```
3. Select **GitHub.com** and **Login with a web browser**, then follow all subsequent instructions.
````
````{tabbed} MacPorts
1. Launch **Terminal** from *Applications*.
2. Install the GitHub CLI by running the following commands:
    ```bash
    sudo port install gh
    ```
2. Run the following command to configure the GitHub CLI:
    ```bash
    gh auth login
    ```
3. Select **GitHub.com** and **Login with a web browser**, then follow all subsequent instructions.
````
`````


## Install and Configure Miniconda

Miniconda is a lightweight Python distribution that comes bundled with the Conda package manager. You might have also heard of Anaconda, which is a beefier version of Miniconda that also ships with numerous data-science-related Python packages preinstalled. We will not need most of those packages and the packages included in Anaconda are likely to be incompatible with various geospatial packages, which will lead to problems later in the semester. Hence, we will install the lightweight Miniconda instead and manually add any packages we need along the way. The following will guide you through installing Miniconda and configuring your base environment. Do not worry if you do not fully understand what is going on at this point. We will talk about Conda and Python package management later in the course, after which it will all make more sense.

```{warning}
You must completely uninstall any previous Anaconda or Miniconda installations before proceeding with these instructions to avoid any potential issues. Please contact the course staff if you are unsure how to do that.
```

```{caution}
After completing this setup, your base environment will be configured and you should **NOT** install any additional packages into it. We will talk about the importance of that later in the course.
```

````{tabbed} Windows
1. [**Click here**](https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe) to download the latest 64-bit Minconda installer for Windows.
2. Run the downloaded installer and select the following options:
    - Install for **Just Me (recommended)**
    - Accept the default destination folder
    - **DO NOT** add Miniconda3 to PATH *(keep this __unchecked__)*
    - **DO** register Miniconda3 as your default Python *(keep this __checked__)*
3. Once the installer has finished, open **Anaconda PowerShell Prompt** from *Start > Anaconda3*.
4. Using **Anaconda PowerShell Prompt**, run the following commands to configure your base environment:
    ```powershell
    conda config --add channels conda-forge
    conda config --set channel_priority strict
    conda update conda --yes
    conda install mamba --yes
    mamba update --all --yes
    mamba install jupyterlab>=3 nb_conda_kernels --yes
    ```
    *Feel free to just copy all of the commands and paste them into the prompt. All but the last line should automatically run one after the other. __You will need to press Enter to run the last command once all previous commands have finished.__*
````
````{tabbed} macOS
1. Open **Terminal** from *Applications*.
2. Download the latest Miniconda install script for macOS by running the following command:
    ```bash
    curl -L -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
    ```
    If that does not work, try this alternative download command:
    ```bash
    wget https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
    ```
3. Once the download has finished, run the following command to start the installation process:
    ```bash
    bash Miniconda3-latest-MacOSX-x86_64.sh
    ```
4. Follow the installation prompts and accept all default settings.
5. Answer **YES** to *Do you wish the installer to initialize Miniconda3 by running conda init?*
6. Once the installer has finished, close your terminal and restart it via *Applications > Terminal*.
7. The line where you enter your commands should now begin with **`(base)`**.
    - *__STOP__ and contact course staff if that is not the case*.
8. Run the following commands to configure your base environment:
    ```bash
    conda config --add channels conda-forge
    conda config --set channel_priority strict
    conda update conda --yes
    conda install mamba --yes
    mamba update --all --yes
    mamba install jupyterlab>=3 nb_conda_kernels --yes
    ```
    *Feel free to just copy all of the commands and paste them into the terminal. All but the last line should automatically run one after the other. __You will need to press Return to run the last command once all previous commands have finished.__*
````


## Install Windows Terminal and PowerShell Core

```{note}
Obviously, the following is for Windows users only. Others are welcome to [**skip ahead**](#install-visual-studio-code-python-extensions) to the next section.
```

Windows is often criticized amongst developers for having a clunky and uncomfortable command-line interface. However, that has changed in recent years with the release of Windows Terminal and PowerShell Core – a new and improved cross-platform version of PowerShell. (Note that this is different and actually completely separate from the PowerShell included in Windows by default, also known as Windows PowerShell.) To guarantee that you will have the best and most comfortable possible command-line interface on your Windows computer, let us install Windows Terminal along with PowerShell Core and configure them to work well with both Conda and Git.

Both Windows Terminal and PowerShell Core are available from the [Microsoft Store](https://www.microsoft.com/en-us/store/apps/windows). Use the links below install them in the order specified – PowerShell Core **before** Windows Terminal.

1. Install **PowerShell Core**: <https://www.microsoft.com/en-us/p/powershell/9mz1snwt0n5d>
2. Install **Windows Terminal**: <https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701>

### Configure Windows Terminal and PowerShell Core

Once you have installed both PowerShell Core and Windows Terminal, configure them to automatically initiate Conda and display Git repository status by doing the following.

1. *Right-click* on the **Start** button and select **Windows PowerShell (Admin)**.
2. Click **yes** when asked for confirmation, enter an **administrator** password if needed.
3. Run the following commands to configure the prerequisites needed to install modules from the  [PowerShell Gallery](https://www.powershellgallery.com/):
    ```powershell
    Install-PackageProvider -Name NuGet -Force
    Install-Module PowerShellGet -Scope CurrentUser -Force -AllowClobber
    ```
4. After both commands have finished running, close Windows PowerShell.
5. Open the **Start** menu and scroll down until you see **Windows Terminal**.
6. *Right-click* on **Windows Terminal** in the Start menu and select *More > __Run as administrator__*.
7. Click **yes** when asked for confirmation, enter an **administrator** password if needed.
8. If the first line reads **`Windows Powershell`** instead of **`Powershell 7.X.X`**, **STOP** and contact course staff.
9. Run the following commands to install and configure [PoSh-Git](https://github.com/dahlbyk/posh-git) (a Git status module for PowerShell):
    ```powershell
    PowerShellGet\Install-Module posh-git -Scope CurrentUser -AllowPrerelease -Force
    Add-PoshGitToProfile
    ```
10. Run the following command to open your PowerShell profile configuration file in Notepad:
    ```powershell
    notepad (Resolve-Path "~\Documents\PowerShell\Microsoft.PowerShell_profile.ps1")
    ```
11. Confirm that the file contents are as follows, **STOP** and contact course staff if that is not the case:
    ```powershell
    Import-Module posh-git
    ```
12. Modify the file so that it contains the following instead:
    ```powershell
    Import-Module posh-git
    Invoke-Expression (Resolve-Path "~\miniconda3\shell\condabin\conda-hook.ps1")
    Invoke-Conda activate (Resolve-Path "~\miniconda3")
    Clear-Host
    ```
13. Save the file via *File > Save* or by pressing **Ctrl+S**.
14. Close Notepad.
15. Close **Windows Terminal** and restart it via ***Start > Windows Terminal***.
16. Confirm that the line where you enter your commands now begins with **`(base)`**.
    - **IF YES**, you are all set and should now use **Windows Terminal** for anything command-line related.
    - **IF NOT**, contact the course staff for assistance.


## Install Visual Studio Code Python Extensions
Visual Studio Code is extremely modular and extensible, meaning that it has numerous extensions available that increase or improve its usability. The following will guide you through installing and configuring a couple Python-related extensions that ought to make your life easier in this course.

````{tabbed} Windows
1. Launch **Visual Studio Code** via *Start > Visual Studio Code*.
2. With Visual Studio Code open, press **Ctrl+P** to launch **Quick Open**.
3. Type **`ext install ms-python.python`** and press **Enter**.
4. Check on the status of the installation on the panel in the left side.
5. Once the extension has installed, launch **Quick Open** again by pressing **Ctrl+P**.
6. Type **`ext install ms-python.vscode-pylance`** and press **Enter**.
7. Check on the status of the installation on the panel in the left side and wait for the extension to install.
8. Launch the **Command Palette** via *View > Command Palette* or by pressing **Ctrl+Shift+P**.
9. Type *terminal select default shell* into the Command Palette.
10. Select **Terminal: Select Default Shell** and then **PowerShell (store)**.
11. Open the **Command Palette** via *View > Command Palette* or by pressing **Ctrl+Shift+P**.
12. Type *python select interpreter* into the Command Palette.
13. Select **Python: Select Interpreter** and wait for the Command Palette to reopen.
14. Once the Command Palette reopens, select **Python 3.X.X 64-bit (conda)**.
15. Open the **Command Palette** via *View > Command Palette* or by pressing **Ctrl+Shift+P**.
16. Type *python select linter* into the Command Palette.
17. Select **Python: Select Linter** and then **Disable Linting**.
18. Open the **Command Palette** via *View > Command Palette* or by pressing **Ctrl+Shift+P**.
19. Type *open settings json* into the Command Palette.
20. Select **Preferences: Open Settings (JSON)**.
21. Once the `settings.json` file opens, confirm that its contents **resemble** the following *(will not be exactly the same)*:
    ```json
    {
        "python.pythonPath": "C:\\Users\\...\\miniconda3\\python.exe",
        "terminal.integrated.shell.windows": "C:\\Users\\...\\pwsh.exe",
        "python.linting.enabled": false
    }
    ```
22. After **`"python.linting.enabled": false`** type a comma and then press **Enter**.
23. Type the following on the new line: **`"python.languageServer": "Pylance"`**
24. Now your `settings.json` file should **resemble** the following:
    ```json
    {
        "python.pythonPath": "C:\\Users\\...\\miniconda3\\python.exe",
        "terminal.integrated.shell.windows": "C:\\Users\\...\\pwsh.exe",
        "python.linting.enabled": false,
        "python.languageServer": "Pylance"
    }
    ```
25. Save the file via *File > Save* or by pressing **Ctrl+S**.
26. Close the `settings.json` tab, then close Visual Studio Code.
````
````{tabbed} macOS
1. Launch **Visual Studio Code**.
2. With Visual Studio Code open, press **Ctrl+P** to launch **Quick Open**.
3. Type **`ext install ms-python.python`** and press **Return**.
4. Check on the status of the installation on the panel in the left side.
5. Once the extension has installed, launch **Quick Open** again by pressing **Ctrl+P**.
6. Type **`ext install ms-python.vscode-pylance`** and press **Return**.
7. Check on the status of the installation on the panel in the left side and wait for the extension to install.
8. Launch the **Command Palette** via *View > Command Palette* or by pressing **Ctrl+Shift+P**.
9. Type *python select interpreter* into the Command Palette.
10. Select **Python: Select Interpreter** and wait for the Command Palette to reopen.
11. Once the Command Palette reopens, select **Python 3.X.X 64-bit ('base':conda)**.
12. Launch the **Command Palette** via *View > Command Palette* or by pressing **Ctrl+Shift+P**.
13. Type *python select linter* into the Command Palette.
14. Select **Python: Select Linter** and then **Disable Linting**.
15. Launch the **Command Palette** via *View > Command Palette* or by pressing **Ctrl+Shift+P**.
16. Type *open settings json* into the Command Palette.
17. Select **Preferences: Open Settings (JSON)**.
18. Once the `settings.json` file opens, confirm that its contents **resemble** the following *(will not be exactly the same)*:
    ```json
    {
        "python.defaultInterpreterPath": "/users/.../miniconda3/bin/python",
        "python.linting.enabled": false
    }
    ```
19. After **`"python.linting.enabled": false`** type a comma and then press **Return**.
20. Type the following on the new line: **`"python.languageServer": "Pylance"`**
21. Now your `settings.json` file should **resemble** the following:
    ```json
    {
        "python.defaultInterpreterPath": "/users/.../miniconda3/bin/python",
        "python.linting.enabled": false,
        "python.languageServer": "Pylance"
    }
    ```
22. Save the file via *File > Save* or by pressing **Ctrl+S**.
23. Close the `settings.json` tab, then close Visual Studio Code.
````


## Jazz Up your Terminal (Optional)

You will be spending a lot of time working on the command line in this course and you will quickly realize that your terminal is one of the most powerful tools in your disposal. However, right now it looks kind of dull...

![old school terminal](/img/posh-git.png)

Depending on your operating system and particular configuration, it might look even more bland than that. But it does not have to be this way! Your terminal window does not need to look like it is perpetually stuck in the 1980s. Instead, it could look like this...

![beautiful colorful terminal](/img/powerline.png)

Making your terminal window more beautiful and colorful like this will not add any additional functionality. Nor will it make you a better programmer. However, it will make you feel like a better programmer and make the time spent staring at your terminal window at least somewhat more enjoyable. (And that might just make you a better programmer in the long run.)

````{tabbed} Windows
**Install the Cascadia Code PL font:**
1. Navigate to: <https://github.com/microsoft/cascadia-code/releases/latest>
2. Download the **`CascadiaCode-XXXX.XX.zip`** file located under **Assets**.
3. Extract the contents of the downloaded ZIP-file to a suitable location.
4. Open the extracted folder, then open the **`ttf`** folder.
5. *Right-click* on **`CascadiaCodePL.ttf`** and select **Install*.

**Configure Windows Terminal to use the Cascadia Code PL font:**
1. Launch **Windows Terminal** via *Start > Windows Terminal*.
2. Click on the down arrow to the right of the plus sign and select **Settings** from the drop-down menu.
3. A `settings.json` file for will open in a text editor. *(If prompted to select a text editor, choose Visual Studio Code.)*
4. Find the line **`// Put settings here that you want to apply to all profiles.`** in the **"`defaults"`** section.
5. Place the line **`"fontFace": "Cascadia Code PL"`** into the **`"defaults"`** section so that it looks like this:
    ```
    "defaults":
    {
        // Put settings here that you want to apply to all profiles.
        "fontFace": "Cascadia Code PL"
    },
    ```
7. Save the file via *File > Save* or by pressing **Ctrl+S**.
8. Close the `settings.json` file or tab (depending on your text editor).

**Configure the Visual Studio Code terminal to use the Cascadia Code PL font:**
1. If not already open, launch **Visual Studio Code** via *Start > Visual Studio Code*.
2. Open the **Command Palette** via *View > Command Palette* or by pressing **Ctrl+Shift+P**.
3. Type *open settings json* into the Command Palette.
4. Select **Preferences: Open Settings (JSON)**.
5. A `settings.json` file resembling the following will open:
    ```json
    {
        "python.pythonPath": "C:\\Users\\...\\miniconda3\\python.exe",
        "terminal.integrated.shell.windows": "C:\\Users\\...\\pwsh.exe",
        "python.linting.enabled": false,
        "python.languageServer": "Pylance"
    }
    ```
6. After **`"python.languageServer": "Pylance"`** type a comma and then press **Enter**.
7. Type the following on the new line: **`""terminal.integrated.fontFamily": "Cascadia Code PL"`**
8. Now your `settings.json` file should look like this:
    ```json
    {
        "python.pythonPath": "C:\\Users\\...\\miniconda3\\python.exe",
        "terminal.integrated.shell.windows": "C:\\Users\\...\\pwsh.exe",
        "python.linting.enabled": false,
        "python.languageServer": "Pylance",
        "terminal.integrated.fontFamily": "Cascadia Code PL"
    }
    ```
9. Save the file via *File > Save* or by pressing **Ctrl+S**.
10. Close the `settings.json` tab, then close Visual Studio Code.

**Install and configure Oh-My-PoSh:**
1. Launch **Windows Terminal** via *Start > Windows Terminal*.
2. Run the following commands to install Oh-My-PoSh and download a suitable theme:
    ```powershell
    Install-Module PSReadLine -AllowPrerelease -Scope CurrentUser -Force
    Install-Module oh-my-posh -Scope CurrentUser -MaximumVersion 2.1 -Force
    New-Item "~\Documents\PowerShell\PoshThemes\paradox-cascadia.psm1" -Force
    curl -L "https://raw.githubusercontent.com/ukukas/paradox-cascadia/main/paradox-cascadia.psm1" -o (Resolve-Path "~\Documents\PowerShell\PoshThemes\paradox-cascadia.psm1")
    ```
3. Run the following command to open your PowerShell profile configuration file in Notepad:
    ```powershell
    notepad (Resolve-Path "~\Documents\PowerShell\Microsoft.PowerShell_profile.ps1")
    ```
4. Modify the file so that it contains the following:
    ```powershell
    Import-Module posh-git
    Import-Module oh-my-posh
    Set-Theme paradox-cascadia
    Invoke-Expression (Resolve-Path "~\miniconda3\shell\condabin\conda-hook.ps1")
    Invoke-Conda activate (Resolve-Path "~\miniconda3")
    Clear-Host
    ```
5. Save the file via *File > Save* or by pressing **Ctrl+S**.
6. Close Notepad.
7. Close **Windows Terminal** and restart it via ***Start > Windows Terminal***.
8. Confirm that your terminal now looks like the following. Contact the course staff for assistance if not.
    ![beautiful colorful terminal](/img/paradox-cascadia.png)

Note that there are numerous other themes available for Oh-My-PoSh as well. However, most of them require additional configuration or a specialized [Nerd Font](https://www.nerdfonts.com/) to display properly. Right now we configured Oh-My-PoSh to use a custom theme that works well with the Cascadia Code PL font, which is an official Microsoft font designed for use with Windows Terminal. Once you are more comfortable with PowerShell and its configuration, feel free to explore the [Oh-My-PoSh documentation ](https://github.com/JanDeDobbeleer/oh-my-posh) and set up a different theme of your liking.
````
```{tabbed} macOS
There are two frameworks available for you to customize and beautify your terminal – [**Oh-My-Zsh**](https://ohmyz.sh/) and [**Oh-My-Bash**](https://ohmybash.nntoan.com/). Which you should use depends on your default shell. If you are using macOS 10.15 Catalina or newer and the line where you enter your commands in Terminal ends with a percent sign (`%`), then you are likely using Zsh. And if you are using macOS 10.14 Mojave or older and the line where you enter your commands in Terminal ends with a dollar sign (`$`), then you are probably using Bash. However, various configuration changes can alter both your default shell and its appearance. Hence, to make sure you know which is your default shell, do the following:

1. Launch **Terminal** from *Applications*.
2. Run the following command and take note of the response:
    ```bash
    echo $0
    ```

- If the response is **`zsh`**, then you are running **Zsh** and should check out [**Oh-My-Zsh**](https://ohmyz.sh/).
- If the response is **`bash`**, then you are running **Bash** and should check out [**Oh-My-Bash**](https://ohmybash.nntoan.com/).

Use the links above and follow the instructions corresponding to your default shell to customize your terminal to your liking. Note that some themes might require you to install a custom font. Once you have finalized the configuration, you might need to do the following in order to be able to see your Conda environment in your Terminal again.

1. Launch **Terminal** from *Applications*.
2. Run the following commands:
    ```bash
    source miniconda3/bin/activate
    conda init
    ```
```