# Environment Package Managers

## WSL (Ubuntu)

## Java (JDK)

`update-alternatives` is used to manage multiple versions of Java on a Linux system. Here’s how to use it:

### **1. Check Installed Java Versions**
Run the following command to see which Java versions are installed:
```sh
update-alternatives --display java
```
or
```sh
update-alternatives --list java
```

If no alternatives are set, you'll need to manually add them.

### **2. Add Java Versions (If Needed)**
If Java isn't already managed by `update-alternatives`, add different versions manually:
```sh
sudo update-alternatives --install /usr/bin/java java /path/to/java1 1
sudo update-alternatives --install /usr/bin/java java /path/to/java2 2
```
For example, if you installed Java in `/usr/lib/jvm/`, you might run:
```sh
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/java-17-openjdk-amd64/bin/java 1
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/java-11-openjdk-amd64/bin/java 2
```

### **3. Choose Default Java Version**
To set the default Java version interactively:
```sh
sudo update-alternatives --config java
```
You'll see a list like this:
```
There are 2 choices for the alternative java (providing /usr/bin/java).

  Selection    Path                                         Priority   Status
------------------------------------------------------------
  0            /usr/lib/jvm/java-17-openjdk-amd64/bin/java   100       auto mode
  1            /usr/lib/jvm/java-11-openjdk-amd64/bin/java   200       manual mode

Press <enter> to keep the current choice[*], or type selection number:
```
Enter the number of the version you want.

### **4. Verify Java Version**
After selecting the version, verify it with:
```sh
java -version
```

### **5. Update Other Java Components (Optional)**
If you need to update other Java components like `javac`, do:
```sh
sudo update-alternatives --config javac
```

This ensures that all Java-related tools match your selected version.

## Node

```bash
# Download and install nvm:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.2/install.sh | bash

# in lieu of restarting the shell
\. "$HOME/.nvm/nvm.sh"

# Download and install Node.js:
nvm install 22

# Verify the Node.js version:
node -v # Should print "v22.14.0".
nvm current # Should print "v22.14.0".

# Verify npm version:
npm -v # Should print "10.9.2".
```

## Python

Download the latest version of `Anaconda Distribution` by opening a terminal and running one of the following commands (depending on your Linux architecture):

- Linux x86
- AWS Graviton2/ARM64
- IBMZ/LinuxOne/s390x

```bash
curl -O https://repo.anaconda.com/archive/Anaconda3-2024.10-1-Linux-x86_64.sh
```

To download a different version

(Recommended) Verify the integrity of your installer to ensure that it was not corrupted or tampered with during download.

How do I verify my installer’s integrity?

Install Anaconda Distribution by running one of the following commands (depending on your Linux architecture):

- Linux x86
- AWS Graviton2/ARM64
- IBMZ/LinuxOne/s390x

```bash
bash ~/Anaconda3-2024.10-1-Linux-x86_64.sh
```

- Press Return to review the Anaconda’s Terms of Service (TOS). Then press and hold Return to scroll.

- Enter yes to agree to the TOS.

- Press Return to accept the default install location (PREFIX=/Users/<USER>/anaconda3), or enter another file path to specify an alternate installation directory. The installation might take a few minutes to complete.

Choose an initialization options:

- Yes - conda modifies your shell configuration to initialize conda whenever you open a new shell and to recognize conda commands automatically.
- No - conda will not modify your shell scripts. After installation, if you want to initialize, you must do so manually.

For more information, see Manual shell initialization.
The installer finishes and displays, `“Thank you for installing Anaconda3!”`

Close and re-open your terminal window for the installation to fully take effect, or use the following command to refresh the terminal, depending on your shell:

- Bash
- Zsh
- Fish

```bash
source ~/.bashrc
```
