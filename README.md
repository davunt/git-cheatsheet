# GIT Cheatsheet

## Config
* `git config --global -e` - edit git globe config (name, email, default git editor, line endings)
* `git config --global user.name “David H”`
* `git config --global user.email  my@email.com`

### core.autocrlf
* `git config --gloabl core.autocrlf true`  - Windows
* `git config --gloabl core.autocrlf input` - Mac/Linux
* On Windows end of file is CR/LF
* On Mac and Linux it’s just LF
* Windows machines should be set to push code with just LF, and pull down with CR/LF
* On Mac_Linux, it should convert CR_LF to LF if CR/LF is present

## Setup
* `git init`
* `git add filename/*/*.txt`
* `git commit`
	* `git commit`
		* will open default text editor
		* first line is short description
		* line break
		* next line is long description
	* `git commit -m “”`
	* `git commit -am “”` - add and commit all modified files
* `git ls-files` - Show information about files in the index and the working tree
* git rm

## .gitignore
* list files or directories that you want git to ignore
* git will not ignore a file that you had already committed to your repo, even after adding it to gitignore (because they are already tracked by git)
* Solution: `git rm`
	* `git rm -h` - help

## git diff
* `git diff --staged` - the diff for all changes staged (added)
* `git diff` - the diff of all files not staged (added)
* Set VSCode at diff tool
	* `git config --global diff.tool vscode`
	* `git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"`
* `git difftool`

## git log
* view git commit history
* `git log --oneline`

## git show
* display changes made in a commit
* `git show <commit hash>/HEAD/HEAD~1(back one from head)`
* `git show <commit>:<file>` - show file at that commit
	* e.g. `git show HEAD~1:package.json`

## Undo…
* add
	* `git reset file/dir `
* commit
	* `git reset —-soft HEAD~1` - will preserve changes done to your files
	* `git reset —-hard HEAD~1` - will not preserve changes
* push
	* `git reset <commit> —-hard`
	* `git push origin -f`
	* [How to remove a commit that is already pushed to Github | @samwize](https://samwize.com/2014/01/15/how-to-remove-a-commit-that-is-already-pushed-to-github/)
