# learning cobra

The code that you will find in this sub project is not intended to work, it might, but don't count on it.

Failure is the acceptable and likely option here.

## resources
* [the source - cobra's github project](https://github.com/spf13/cobra)
* [logging and cobra blog post](https://le-gall.bzh/post/go/integrating-logrus-with-cobra/)

## getting started - following the docs

Using the documents provided by cobra to get a new application started

```bash
export cobra_dir=$(pwd)
export PATH="${PATH}:/Users/${USER}}/go/bin" 

# /Users/primusdj/go/src/github.com/devopsaha/go/learning/cobra/license
mkdir -p "${cobra_dir}/license" && cd "${cobra_dir}/license"

# go module initialize
go mod init github.com/devopsaha/go/learning/cobra/license

# get the cobra binary
go get github.com/spf13/cobra/cobra

cobra init --pkg-name github.com/devopsaha/go/learning/cobra/license

```

The project has been initialized, the cobra cli framework has opinions, several sources recommend to just lean into them.  
So lets lean.  My thoughts on this cli is to build a simple tool that will generate a license file.  Not sure why this,  
but when doing these kind of learning projects initializing git projects and other tooling it might be neat to have a  
tool that can seed the `LICENSE` file with the license you want.

Here are some of the commands that would be nice:

* license `get`
* license `check`
* license `swap`
* license `rm`

Add the above commands to our project:
```bash
cobra help add
cobra add get
cobra add check
cobra add swap
cobra add rm
```

The app is done... not really, but the above commands can be run `go run main.go get` will output `get called`.

There's also the ability to configure cobra to initialize the commands and flags using a `~/.cobra.yaml` file.

But in this case small steps.  Lets get into the license code.