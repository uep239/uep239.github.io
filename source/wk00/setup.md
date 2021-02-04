# Configuring the Course Environment

The following will walk you thorough configuring your **personal Windows or macOS** computer into a comfortable geospatial programming environment. Note that detailed instructions are not provided for **Linux** users as we assume you know that you are doing. Please contact the course staff if you do not have access to a suitable computer **on which you have administrative privileges** or if you need additional assistance with the setup. (Linux users are also welcome to reach out.)

In addition to configuring certain system settings, we will be installing the following software:

- [**Thonny**](https://thonny.org/) – a beginner-friendly integrated development environment (IDE) for Python
- [**Google Chrome**](https://www.google.com/chrome/) or [**Mozilla Firefox**](https://www.mozilla.org/en-US/firefox/new/) – required to run [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) without any issues
- [**Miniconda**](https://docs.conda.io/en/latest/miniconda.html) – a lightweight Python distribution that comes bundled with the [Conda](https://docs.conda.io/en/latest/) package manager
- [**Visual Studio Code**](https://code.visualstudio.com/) (also known as VS Code) – a powerful code-friendly text editor with many useful features
- [**Git**](https://git-scm.com/) – the most widely used distributed version control software
- [**Windows Terminal**](https://docs.microsoft.com/en-us/windows/terminal/) and [**PowerShell Core**](https://docs.microsoft.com/en-us/powershell/) – the next-generation command-line interface for Windows

If you already happen to have any of the aforementioned software installed and configured, please carefully review the instructions below to see what configuration I recommend for this course and will assume you have. All course materials after this point will assume the following configuration and if yours differs, you want to make sure you are aware of the differences and are able to circumnavigate any potential issues that might result. Also note the following:

- If you have worked with code before and already have a favorite Python-friendly text editor and/or IDE installed, feel free to skip the Thonny and/or Visual Studio Code installation and use your preferred application(s) instead.
- If you are an experienced Conda user with a preexisting Anaconda/Miniconda installation, there is no need to change your current configuration at this time. Just make sure you have `jupyterlab>=3` installed, as we will be using it soon.
- If you are not too comfortable with Conda package manager, it is highly recommended that you completely uninstall any preexisting Anaconda or Miniconda installations and start over with a clean sheet.
- It goes without saying, but the Windows Terminal and PowerShell Core section applies to Windows users only.

Please perform all installations and configuration changes in the order they are listed. Toggle the tab corresponding to your operating system to view the appropriate instructions.

```{note}
Instead of manually typing the commands in the instructions into Terminal or PowerShell, you can just copy and paste the command, and then press **Enter/Return** to run it.
```


## Configure System Preferences

Both the Windows and macOS operating systems are configured for the average user by default, with many useful advanced features either disabled or hidden. Please follow the instructions below to show hidden files and filename extensions, and allow the installation and execution of various third-party applications and scripts.

```{danger}
The following will make your system more vulnerable to malicious scripts and applications. Only install applications and execute scripts that you received from a trustworthy source. **Do not execute scripts you do not understand!**
```

````{tabbed} Windows
**Show hidden files and filename extensions**

1. Open **File Explorer**
2. Select the **View** tab
3. In the *Show/Hide* section, ensure the following boxes are **checked**
    - ***File name extensions***
    - ***Hidden items***

**Set PowerShell as your default shell**

1. *Right-click* on your taskbar and click on **Taskbar settings**
2. Ensure *Replace Command Prompt with Windows Powershell in the menu when...* is toggled **ON**

**Allow the execution of third-party scripts**

1. *Right-click* on the start button and select **Windows PowerShell (Admin)**
2. Click **yes** when asked for confirmation, enter an **administrator** password if needed
3. Run the following command (*either type or copy and paste, then press __Enter__ to run*)
    ```powershell
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
    ```
4. When asked for confirmation, type **`A`** and press **Enter**
````
````{tabbed} macOS
**Show filename extensions and configure Finder**

1. Open **Finder** and ensure that *View > Show Path Bar* is **checked**
2. Then go to *Finder > Preferences...*
2. In the *General* section, ensure all items under ***Show these items on the desktop*** are **checked**
3. In the *Advanced* section, ensure ***Show all filename extensions*** is **checked**

**Show hidden files**

1. Open **Terminal** from *Applications*
2. Run the following command (*either type or copy and paste, then press __Return__ to run*)
    ```sh
    defaults write com.apple.finder AppleShowAllFiles YES
    ```

**Allow the installation of third-party applications**
1. Open **Terminal** from *Applications*
2. Run the following command (*either type or copy and paste, then press __Return__ to run*)
    ```sh
    sudo spctl --master-disable
    ```
3. When prompted, enter your **administrator** password
4. Go to *System Preferences > Security and Privacy*
4. Click the ***padlock*** in the bottom, enter your **administrator** password again if needed
5. Near the bottom of the *General* tab, select **Anywhere** under ***Allow apps downloaded from***
````


## Install Thonny and a Suitable Web Browser

**Thonny** is a beginner-friendly integrated development environment (IDE) for Python that is actually written in Python and comes bundled with its own self-contained Python environment. To install Thonny on your computer, download a suitable installer from [**tonny.org**](https://thonny.org/) and accept all default settings.

If you do not already primarily use the [**Google Chrome**](https://www.google.com/chrome/) or [**Mozilla Firefox**](https://www.mozilla.org/en-US/firefox/new/) web browser, you should install one of them and set it as your default browser. Other browsers like Edge or Safari might not be compatible with the [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) interactive notebook interface or the interactive sections of the course website.


## Install and Configure Miniconda

Miniconda is a lightweight Python distribution that comes bundled with the Conda package manager. You might have also heard of Anaconda, which is a beefier version of Miniconda that also ships with numerous data-science-related Python packages preinstalled. We will not need most of those packages and the packages included in Anaconda are likely to be incompatible with various geospatial packages, which will lead to problems later in the semester. Hence, we will install the lightweight Miniconda instead and manually add any packages we need along the way. The following will guide you through installing Miniconda and configuring your base environment. Do not worry if you do not fully understand what is going on at this point. We will talk about Conda and Python package management in the course, after which it will all make more sense.

```{warning}
You must completely uninstall any previous Anaconda or Miniconda installations before proceeding with these instructions to avoid any potential issues. Please contact the course staff if you are unsure how to do that.
```

```{caution}
After completing this setup, your base environment will be configured and you should **not** install any additional packages into it. We will talk about the importance of that later in the course.
```

````{tabbed} Windows
1. [**Click here**](https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe) to download the latest 64-bit Minconda installer for Windows (exe)
2. Run the downloaded installer and select the following options
    - Install for **Just Me (recommended)**
    - Accept the default destination folder
    - **DO NOT** add Miniconda3 to PATH (keep this **unchecked**)
    - **DO** register Miniconda3 as your default Python (keep this **checked**)
3. Once the installer has finished, open **Anaconda PowerShell Prompt** from *Start > Anaconda3*
4. Using **Anaconda PowerShell Prompt**, run the following commands to configure your base environment
    ```powershell
    conda config --add channels conda-forge
    conda config --set channel_priority strict
    conda update conda --yes
    conda install mamba --yes
    mamba update --all --yes
    mamba install jupyterlab>=3 nb_conda_kernels --yes
    ```
    *Feel free to just copy all of the commands and paste them into the prompt. All but the last line should automatically run one after the other. You will need to press Enter to run the last command once all previous commands have finished.*
````
````{tabbed} macOS
1. Open **Terminal** from *Applications*
2. Download the latest Miniconda install script for macOS by running the following command
    ```sh
    curl -L -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
    ```
3. Once the download has finisher, run the following command to start the installation process
    ```sh
    bash Miniconda3-latest-MacOSX-x86_64.sh
    ```
4. Follow the installation prompts and accept all default settings
5. Answer **YES** to *Do you wish the installer to initialize Miniconda3 by running conda init?*
6. Once the installer has finished, close your terminal and restart it via *Applications > Terminal*
7. The line where you enter your commands should now begin with **`(base)`**
    - *__STOP__ and contact course staff if this is not the case*
8. Run the following commands to configure your base environment
    ```sh
    conda config --add channels conda-forge
    conda config --set channel_priority strict
    conda update conda --yes
    conda install mamba --yes
    mamba update --all --yes
    mamba install jupyterlab>=3 nb_conda_kernels --yes
    ```
    *Feel free to just copy all of the commands and paste them into the terminal. All but the last line should automatically run one after the other. You will need to press Return to run the last command once all previous commands have finished.*
````


## Install Visual Studio Code

```{tabbed} Windows
Windows instructions here
```
```{tabbed} macOS
MacOS instructions here
```


## Install and Configure Git

```{attention}
You will need to create GitHub account before proceeding (unless you already have one): [**github.com/join**](https://github.com/join)
```

### Install and Git and Configure Basic Settings

```{tabbed} Windows
Windows instructions here
```
```{tabbed} macOS
MacOS instructions here
```

### Configure an SSH Key for GitHub Authentication

```{tabbed} Windows
Windows instructions here
```
```{tabbed} macOS
MacOS instructions here
```

### Add Git Status to your Terminal

```{tabbed} Windows
Windows instructions here
```
```{tabbed} macOS
MacOS instructions here
```

### Install the GitHub CLI (Optional)

```{tabbed} Windows
Windows instructions here
```
````{tabbed} macOS
```{tabbed} Homebrew
Windows instructions here
```
```{tabbed} MacPorts
Windows instructions here
```
```{tabbed} Binary
Windows instructions here
```
````


## Install Windows Terminal and PowerShell Core


## Install the Visual Studio Code Python Extension


## Jazz Up your Terminal (Optional)

```{tabbed} Windows
Windows instructions here
```
```{tabbed} macOS
MacOS instructions here
```