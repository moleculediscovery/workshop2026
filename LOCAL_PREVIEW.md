# Local preview

To preview the GitHub Pages site on Windows:

1. Install Ruby with Devkit from [RubyInstaller for Windows](https://rubyinstaller.org/downloads/).
2. Open PowerShell in this directory and install the dependencies:

   ```powershell
   gem install bundler
   bundle install
   ```

3. Start the local server:

   ```powershell
   bundle exec jekyll serve --baseurl=/
   ```

4. Open <http://127.0.0.1:4000/> in your browser. Jekyll rebuilds the site when files change; stop the server with `Ctrl+C`.

The root base URL keeps links working at the root of the local server. The published site continues to use the `/workshop2026` base URL from `_config.yml`.

## Using WSL (Ubuntu)

You can also run the preview in WSL. Install Ruby and the build tools:

```bash
sudo apt update
sudo apt install ruby-full ruby-bundler build-essential zlib1g-dev
```

From the WSL terminal, go to the Windows project folder (mounted under `/mnt/c`):

```bash
cd /mnt/c/Users/Administrator/OneDrive/JKU/ADMISTRATION/ML4Molecule_2026/workshop2026
```

Install the project gems into your WSL home directory, then start Jekyll:

```bash
bundle config set --global path "$HOME/.bundle"
bundle install
bundle exec jekyll serve --baseurl=/ --host 0.0.0.0
```

Open <http://127.0.0.1:4000/> in your Windows browser. Files in `/mnt/c` can be slower to watch; for better performance, keep the project in the WSL filesystem and open it with VS Code's WSL connection.
