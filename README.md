These links are used by Microsoft Store to download the packages:

* https://raw.githubusercontent.com/oneclick/rubyinstaller-releases/release/rubyinstaller-4.0.4-1-x64.exe
* https://raw.githubusercontent.com/oneclick/rubyinstaller-releases/release/rubyinstaller-4.0.4-1-arm.exe

The history of this git repository is non-continous.
Old files are removed from the history, so that only the latest 2 releases are stored.
It's best to configure the local repository with rebase-on-pull like so:
```
git config pull.rebase true 
git pull
```

Release files are updated like so:
```
git-filter-repo --sensitive-data-removal --invert-paths --force --path  rubyinstaller-4.0.2-1-x64.exe
git-filter-repo --sensitive-data-removal --invert-paths --force --path  rubyinstaller-4.0.2-1-arm.exe
git add rubyinstaller-4.0.4-1-*
git commit -am "Add RubyInstaller-4.0.4-1"
git push -f
```
