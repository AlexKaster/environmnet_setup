### Step 1: Install `pyenv` and `pyenv-virtualenv`

1. Install `pyenv`:
   ```zsh
   curl https://pyenv.run | zsh
   ```

2. Install `pyenv-virtualenv`:
   ```zsh
   git clone https://github.com/pyenv/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv
   ```

3. Add `pyenv` and `pyenv-virtualenv` to your `~/.zshrc`:
   ```zsh
   export PATH="$HOME/.pyenv/bin:$PATH"
   eval "$(pyenv init --path)"
   eval "$(pyenv init -)"
   eval "$(pyenv virtualenv-init -)"
   ```

4. Source the file:
   ```zsh
   source ~/.zshrc
   ```

### Step 2: Install the Specific Python Versions You Need

```zsh
pyenv install 3.11.1
pyenv install 3.9.6
```

### Step 3: Create an Isolated Virtual Environment for Each Project

1. Create the virtual environments:
   ```zsh
   pyenv virtualenv 3.11.1 project_env_3_11
   pyenv virtualenv 3.9.6 project_env_3_9
   ```

2. Activate each environment when needed:
   ```zsh
   pyenv activate project_env_3_11
   ```

3. Deactivate the environment:
   ```zsh
   pyenv deactivate
   ```

### Step 4: Set a Local Environment for Each Project Directory

1. Navigate to your project directory:
   ```zsh
   cd /path/to/your/project
   ```

2. Set the local Python version for the project:
   ```zsh
   pyenv local project_env_3_11
   ```

### Step 5: Install Packages as Needed

With each environment active:
```zsh
pip install some_package
```

### Summary of Commands

1. Install Python versions:
   ```zsh
   pyenv install <version>
   ```

2. Create virtual environments with specific Python versions:
   ```zsh
   pyenv virtualenv <version> <env_name>
   ```

3. Activate an environment:
   ```zsh
   pyenv activate <env_name>
   ```

4. Set a local environment for a directory:
   ```zsh
   pyenv local <env_name>