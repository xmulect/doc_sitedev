# Quick build a book


### Build Node.js and package manager

#### Debian based after Jessie (8.0)

GitBook is developed based on Node.js, it can be installed from package management tool of Node.js, npm. 
While npm is only included in the package repository of new Linux release versions. 
*e.g.* after Jessie (8.0) of Debian:

```bash
  sudo apt-get install npm
```

the dependencies will be automatically installed.

Make a symbolic link for `nodejs`, because some applications call it as `node`:

```bash
  sudo ln -s /usr/bin/nodejs /usr/bin/node
```

### Install Gitbook

Install GitBook hosting:
  
```bash
  sudo npm install gitbook-cli -g
```

### Initialize

Initialize in the book root directory,

```bash
  gitbook init
```

First time running, GitBook will download files for creat books.

and we can see the initialization create 2 files: ``README.md`` and ``SUMMARY.md``.
These were the least requirement of GitBook server. 
We can treat ``README.md`` as *Preface* and ``SUMMARY.md`` as *Table of Contents*.

### Push to Github

```bash
  git remote add origin https://github.com/xmulect/doc_sitedev.git
```

```bash
  wget https://raw.githubusercontent.com/github/gitignore/master/GitBook.gitignore
```



