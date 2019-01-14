# Redmine-GitHub_on_GCP
Installing Readmine (http://www.redmine.org/) that integrated with Git/GitHub  hosts on Google Cloud Platform (GCP)
[GitHub - koppen/redmine_github_hook: Allow your Redmine installation to be notify](https://github.com/koppen/redmine_github_hook)


The interactions between the different parts of the process is outlined in the following sequence diagram:![alt tag](https://cloud.githubusercontent.com/assets/6480/3311503/3a789390-f6c5-11e3-804d-d5ca2562799f.png)

## Installation
Major parts rfer from [Redmine GitHub Hook](https://github.com/koppen/redmine_github_hook)

* Step 1
Install the Redmine plugins

```
cd /path/to/redmine/plugins
git clone https://github.com/koppen/redmine_github_hook.git
```

```
cd /path/to/redmine/tmp
touch restart.txt
```

```
 sudo /etc/init.d/apache2 restart
```

Check Redmine Plugins installation or not.
Home--→Administration--→Plugins
![alt tag](https://i.imgur.com/rPQXfXb.jpg)

* Step 2
Add the repository to Redmine
```
(note, this should work whether you want to use Redmine GitHub Hook or not) !!!cliché!!!
```

Login GitHub without password with Deploy keys setting

```
ssh-keygen -t rsa -C amyfanpti@gmail.com
```
![alt tag](https://i.imgur.com/nv6zwnJ.jpg)

repositories on GitHub--→Settings--→Deploy key--→Add deploy key
![alt tag](https://i.imgur.com/h1BMYp1.jpg)

```
$ git clone https://github.com/philip-shen/Redmine-GitHub_on_GCP.git
$ git pull
Already up-to-date.
```

git clone repositor
```
cd /path/to/redmine/repositories
git clone --bare git@github.com:username/repository.git
```

Setting Git on Redmine
![alt tag](https://i.imgur.com/zXP5Fh5.jpg)

Check Repository on Redmine
![alt tag](https://i.imgur.com/oafcMfg.jpg)

* Step 3
Connecting GitHub to Redmine

Webhook on GitHub Configuration


* Step 4 

* Step 5

## Troubleshooting


## Environment Configuration
```
o Ubuntu 16.04.5 LTS (GNU/Linux 4.15.0-1026-gcp x86_64)。
o Apache 2.4。
o MariaDB 10.0.36。
o Ruby 2.4 (via RVM Installation)。
o Rails 5.2 (via GEM Installation)。
o Redmine 4.0.0 (2018-12-09)。
```

## Reference 
* [Redmine GitHub Hook plugin](https://github.com/koppen/redmine_github_hook)
* [HowTo-Redmine 整合 Git/GitHub](https://www.kenming.idv.tw/howto_redmine_integrate_git_and_github/)
* [RedmineとGitHubを連携する](https://codelab.website/redmine-github/)
* [GitHubのリポジトリにDeploy keysを登録してパスワードなしでアクセスする](https://codelab.website/github-deploy-keys/)
* [RedmineとGitHubを連携](https://qiita.com/n_slender/items/54cd282c140fadbbb322)
* [bundle install すると Could not find xxx in any of the sources と怒られる場合の対処法](https://qiita.com/jnchito/items/44ab1df134369ed76911)
* [find_spec_for_exe': can't find gem bundler (>= 0.a) (Gem::GemNotFoundException)](https://stackoverflow.com/questions/47026174/find-spec-for-exe-cant-find-gem-bundler-0-a-gemgemnotfoundexception/47201709)
* [ERROR: Gem bundler is not installed, run `gem install bundler` first](https://stackoverflow.com/questions/12326705/error-gem-bundler-is-not-installed-run-gem-install-bundler-first)
* [Understanding the Gemfile.lock file](https://stackoverflow.com/questions/7517524/understanding-the-gemfile-lock-file)
```
After running the bundle install command, 'Gemfile.lock' is created in the working directory. 
```
* [Bundler 與 Gemfile 設定檔](https://ihower.tw/rails/environments-and-bundler.html#sec8)

* [Error: undefined method `skip_before_filter' for GithubHookController:Class #87](https://github.com/koppen/redmine_github_hook/issues/87)
```
The plugin of version 2.2.0 (installed from gem) works fine with my Redmine v3.4.2 install on Rails v4.2.8, Ruby v2.3.1p112 (2016-04-26).

Note that according to http://www.redmine.org/projects/redmine/wiki/RedmineInstall, Redmine 3.4 should use Rails 4.2.
```

![alt tag]()