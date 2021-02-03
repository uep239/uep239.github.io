# Configuring the Course Environment

The following will walk you thorough configuring your **personal Windows or macOS** computer into a comfortable geospatial programming environment. Note that detailed instructions are not provided for **Linux** users as we assume you know that you are doing. Please contact the course staff if you do not have access to a suitable computer **on which you have administrative privileges** or if you need additional assistance with the setup. (Linux users are also welcome to reach out.)

In addition to configuring certain system settings, we will be installing the following software:

- [**Thonny**](https://thonny.org/) – a beginner-friendly integrated development environment (IDE) for Python
- [**Google Chrome**](https://www.google.com/chrome/) or [**Mozilla Firefox**](https://www.mozilla.org/en-US/firefox/new/) – required to run [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) without any issues
- [**Visual Studio Code**](https://code.visualstudio.com/) (also known as VS Code) – a powerful code-friendly text editor with many useful features
- [**Miniconda**](https://docs.conda.io/en/latest/miniconda.html) – a lightweight data-science-focused Python distribution bundled with the [Conda](https://docs.conda.io/en/latest/) package manager
- [**Git**](https://git-scm.com/) – the most widely used distributed version control software
- [**Windows Terminal**](https://docs.microsoft.com/en-us/windows/terminal/) and [**PowerShell Core**](https://docs.microsoft.com/en-us/powershell/) – the next-generation command-line interface for Windows

If you already happen to have any of the aforementioned software installed and configured, please carefully review the instructions below to see what configuration I recommend for this course and will assume you have. All course materials after this point will assume the following configuration and if yours differs, you want to make sure you are aware of the differences and are able to circumnavigate any potential issues that might result. Also note the following:

- If you have worked with code before and already have a favorite Python-friendly text editor and/or IDE installed, feel free to skip the Thonny and/or Visual Studio Code installation and use your preferred application(s) instead.
- If you arcady actively use Anaconda or Miniconda and/or have modified your base environment, you should carefully review the warnings included with the Miniconda installation instructions to avoid any potential future issues.
- It goes without saying, but the Windows Terminal and PowerShell Core section applies to Windows users only.

Please perform all installations and configuration changes in the order they are listed. Toggle the tab corresponding to your operating system to view the appropriate instructions.


## Configure System Preferences

Both the Windows and macOS operating systems are configured for the average user by default, with many useful advanced features either disabled or hidden. Please follow the instructions below to show hidden files and filename extensions, and allow the installation and execution of various third-party applications and scripts.

```{danger}
The following will make your system more vulnerable to malicious scripts and applications. Only install applications and execute scripts that you received from a trustworthy source. **Do not execute scripts you do not understand!**
```

````{tabbed} Windows
**Show hidden files and filename extensions:**

1. Open **File Explorer**
2. Select the **View** tab
3. In the *Show/Hide* section, ensure the following boxes are **checked**:
    - ***File name extensions***
    - ***Hidden items***

**Set PowerShell as your default shell:**

1. *Right-click* on your taskbar and click on **Taskbar settings**
2. Ensure *Replace Command Prompt with Windows Powershell in the menu when I right-click the start button or...* is toggled **On**

**Allow the execution of third-party scripts:**

1. *Right-click* on the start button and select **Windows PowerShell (Admin)**
2. Click **Yes** when asked for confirmation, enter an **administrator** password if needed
3. Type the following command and press **Enter**
    ```powershell
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
    ```
4. When asked for confirmation, type **`A`** and press **Enter**
````
````{tabbed} macOS
**Show filename extensions and configure Finder:**

1. Open **Finder** and ensure that *View > Show Path Bar* is **checked**
2. Then go to *Finder > Preferences...*
2. In the *General* section, ensure all items under ***Show these items on the desktop*** are **checked**
3. In the *Advanced* section, ensure ***Show all filename extensions*** is **checked**

**Show hidden files:**

1. Open **Terminal** from *Applications*
2. Type the following command and press **Return**
    ```
    defaults write com.apple.finder AppleShowAllFiles YES
    ```

**Allow the installation of third-party applications:**
1. Open **Terminal** from *Applications*
2. Type the following command and press **Return**
    ```
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

## Install and Configure Visual Studio Code

```{tabbed} Windows
Windows instructions here
```
```{tabbed} macOS
MacOS instructions here
```


## Install and Configure Miniconda

```{tabbed} Windows
Windows instructions here
```
```{tabbed} macOS
MacOS instructions here
```


## Install and Configure Git


###  Create a GitHub Account


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
```{tabbed} macOS
MacOS instructions here
```


## Install Windows Terminal and PowerShell Core


## Jazz Up your Terminal (Optional)

```{tabbed} Windows
Windows instructions here
```
```{tabbed} macOS
MacOS instructions here
```