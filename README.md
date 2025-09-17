# Environment Package Managers

## WSL (Ubuntu)

## Java (JDK)

### Managing Multiple Java Versions with `update-alternatives`

Java download guide: [Link](https://adoptium.net/installation/linux)

#### 1. Check Installed Java Versions
```sh
update-alternatives --display java
```
or
```sh
update-alternatives --list java
```

#### 2. Add Java Versions (If Needed)
```sh
sudo update-alternatives --install /usr/bin/java java /path/to/java1 1
sudo update-alternatives --install /usr/bin/java java /path/to/java2 2
```
Example:
```sh
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/java-17-openjdk-amd64/bin/java 1
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/java-11-openjdk-amd64/bin/java 2
```

#### 3. Set Default Java Version
```sh
sudo update-alternatives --config java
```

#### 4. Verify Java Version
```sh
java -version
```

#### 5. Update Other Java Components (Optional)
```sh
sudo update-alternatives --config javac
```

---

## Node.js

### Installation and Management with nvm

```bash
# Install nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.2/install.sh | bash

# Load nvm without restarting shell
\. "$HOME/.nvm/nvm.sh"

# Install Node.js
nvm install 22

# Verify installation
node -v    # Should print "v22.14.0"
nvm current # Should print "v22.14.0"
npm -v     # Should print "10.9.2"
```

---

## Python

### Anaconda Installation

1. **Download Anaconda**:
   ```bash
   curl -O https://repo.anaconda.com/archive/Anaconda3-2024.10-1-Linux-x86_64.sh
   ```

2. **Verify Installer**:
   ```bash
   sha256sum Anaconda3-2024.10-1-Linux-x86_64.sh
   ```

3. **Run Installer**:
   ```bash
   bash Anaconda3-2024.10-1-Linux-x86_64.sh
   ```
   - Accept license terms
   - Choose installation location
   - Select initialization option

4. **Activate Installation**:
   ```bash
   source ~/.bashrc
   ```

### Managing Python Versions with Conda

#### Check Available Python Versions
```sh
conda search python
```

#### Create Environment with Specific Version
```sh
conda create --name py310 python=3.10
```

#### Activate Environment
```sh
conda activate py310
```

#### Verify Python Version
```sh
python --version
```

#### Set Default Python Version
Add to `~/.bashrc`:
```sh
echo "conda activate py310" >> ~/.bashrc
source ~/.bashrc
```

#### Update Python in Environment
```sh
conda activate py310
conda install python=3.11
```

#### Remove Environment
```sh
conda remove --name py310 --all
```

---
