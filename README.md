# How to Install Asymptote on Mac

Note: This guide is designed specifically for Macs with Apple Silicon chips (M1, M2, M3, etc.). If you are using a Mac with an Intel CPU, please be aware that this guide may not be fully compatible with your system.
<hr>

# Option 1: Automated installation via script

I made a small shell script that automates all the steps from <b>Option 2</b>. 
<br>You can download the script directly from this repository: [Installation Script](Install_Asymptote_beta)
<br><br>:warning:Given that I've only tested this script on one machine, I strongly suggest choosing <b>Option 2</b>! This will guide you through the process step by step, making it much easier to identify and address any potential errors. :warning:
<hr>

# Option 2: Step-by-step guide

Follow these steps to install Asymptote on your Mac. This guide assumes you're starting from scratch, without Homebrew or MacTeX installed.

If you already installed Homebrew, you can proceed with step 2 (or step 3, if Homebrew is already working on your machine).

## Step 1: Install Homebrew

Homebrew is a package manager for macOS that simplifies the installation of software.
<br>You can read more about it on the official Website [brew.sh](https://brew.sh) or on Github[homebrew](https://github.com/homebrew)

1. Open the Terminal app.
2. Paste the following command and press Enter:

    ```sh
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

3. You may be prompted to enter your password. Go ahead and do so.
4. Wait until the whole installation process is finished. 

## Step 2: Verify Homebrew Installation

Let's make sure Homebrew is properly installed.

1. Restart your Terminal (you can do this by closing it with the keys `CMD+Q` and opening it again).
2. Type `brew` and press Enter to check if Homebrew commands are recognized.
    - If you see a list of commands and how to use them, proceed to Step 3.
    - If not, enter the following command to add homebrew to your PATH Variables:

        ```sh
        echo "export PATH=/opt/homebrew/bin:$PATH" >> ~/.zshrc
        ```

   Then, restart your Terminal again (`CMD+Q`) and check if the command `brew` is working now.
   If it still doesnt work, please make sure you installed homebrew properly.

## Step 3: Install MacTeX

MacTeX is a distribution of TeX/LaTeX for macOS. Asymptote works with TeX to produce high-quality technical graphics and comes directly with the installation of MacTeX.
<br>You can read more about it on the official Website [tug.org/mactex](https://tug.org/mactex/).

Please note that this installation process can take some time, as it is largely dependent on your network speed. MacTeX requires a download of approximately 6GB. Additionally, ensure that there is sufficient space available on your hard drive before proceeding.

1. Install MacTeX by running:

    ```sh
    brew install --cask mactex
    ```

2. Enter your password if prompted and wait for the installation to finish.

3. Restart your Terminal (`CMD+Q`) after the installation is complete.

## Step 4: Validate Asymptote installation

Now, you're ready to install Asymptote.

1. First, check if the `asy` command is available by typing `asy` in your Terminal. If it's not recognized, proceed with the next step.
2. Add TeX to your PATH by typing the following in command in your Terminal:

    ```sh
    echo "export PATH=/Library/TeX/texbin/:$PATH" >> ~/.zshrc
    ```

3. Restart your Terminal (`CMD+Q`) and type `asy` again. You should see some text about Asymptote now.

## Step 5: Use Asymptote

To work with Asymptote and to check if the installation process was successfull, follow the steps below: 

1. Open your Terminal and navigate to your desired output folder (for example `cd downloads` to navigate to your `Downloads` folder).
2. Try the following command to create a PDF from your `.asy` file.
   If you dont have one, you can download the [example.asy](example.asy) file from this repository, which should only print a circle like in the image below.

    ```sh
    asy -f pdf example.asy
    ```

Replace `example.asy` with the path to an actual Asymptote file (if its in another folder than your Terminal or has another name).

If you get a PDF output, congratulations, you've successfully installed Asymptote on your Mac! ✅<br><br>
![example.asy result](circle.jpg "circle printed with asymptote")
