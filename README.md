### credits
Original work by [Dr Wahl](https://github.com/drwahl) [https://github.com/drwahl/puppet-git-hooks](https://github.com/drwahl/puppet-git-hooks)

## puppet-git-hooks

Git hooks to assist puppet module development.  Client side hooks allow for various checks before commits are staged.  Server side hooks are provided for infrastructural reinforcement of various standarization compliance.

## How to use it
### Pre-Commit
```
git clone \<your project url\>
cd \<your project\>
curl -k https://raw.github.com/Telmo/puppet-git-hooks/master/pre-commit > .git/hooks/pre-commit
chmod 755 .git/hooks/pre-commit
```

### Pre-Receive, Update, Post-Update

Check your git installation for instructions

## What does it do?

### pre-commit

* Verifies syntax of .pp files
* Verifies syntax of .erb templates
* verify syntax of .yaml/.yml files
* _if installed_ runs [puppet-lint](https://github.com/rodjek/puppet-lint) on .pp files

### Puppet-Lint
[puppet-lint](https://github.com/rodjek/puppet-lint) is not required by strongly recommended. I suggest you use the pre-release version wich has the feature to automatically fix **most** of the style issues with puppet manifests.

```
gem install puppet-lint --pre
```

#### options in the pre-commit
* **--no-autoloader\_layout-check** - Skip the autoloader\_layout check
* **--fail-on-warnings** - Return a non-zero exit status for warnings.
* **--with-filename** - Display the filename before the warning
* **--no-80chars-check** - Skip the 80chars check
* **--no-double_quoted_strings-check** - Skip the double_quote_strings check

#### Fixing errors with puppet-lint
```
puppet-lint -f your_file.pp
```