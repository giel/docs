Command gen
===========

Help information: `gopm gen -h` or `gopm help gen`:

```
NAME:
   gen - generate a gopmfile for current Go project

USAGE:
   command gen [command options] [arguments...]

DESCRIPTION:
   Command gen gets dependencies and generates a gopmfile

gopm gen

Make sure you run this command in the root path of a go project.

OPTIONS:
   --tags 		apply build tags
   --local, -l		generate local GOPATH directories
   --verbose, -v	show process details
```
   
### `gopm gen`

- Feature: Generate a gopmfile according current Go project.
- Detail: Get dependencies and list in the gopmfile. 
- Example: `gopm gen`.

#### Usage example

I'm now under `$GOPATH/src/github.com/gogits/gogs`, and I want to generate a gopmfile:

	$ gopm gen
	$ cat .gopmfile
	
Output:

```
[target]
path = github.com/gogits/gogs

[deps]
github.com/beego/memcache = commit:2aea774416
github.com/beego/redigo = commit:856744a0d5
github.com/Unknwon/cae = commit:2e70a1351b
github.com/Unknwon/com = commit:2cbcbc6916
github.com/Unknwon/goconfig = commit:0f8d8dc1c0
github.com/Unknwon/i18n = commit:47baeff8d0
github.com/Unknwon/macaron = 
github.com/codegangsta/cli = commit:7381bc4e62
github.com/go-sql-driver/mysql = commit:8111ee3ec3
github.com/go-xorm/core = commit:750aae0fa5
github.com/go-xorm/xorm = commit:2d8b3135b1
github.com/gogits/gfm = commit:40f747a9c0
github.com/gogits/oauth2 = commit:99cbec870a
github.com/lib/pq = commit:b021d0ef20
github.com/macaron-contrib/cache = commit:204d8e5137
github.com/macaron-contrib/captcha = 
github.com/macaron-contrib/csrf = 
github.com/macaron-contrib/i18n = 
github.com/macaron-contrib/session = 
github.com/macaron-contrib/toolbox = commit:57127bcc89
github.com/mattn/go-sqlite3 = commit:a80c27ba33
github.com/nfnt/resize = commit:581d15cb53
github.com/saintfish/chardet = commit:3af4cd4741

[res]
include = conf|etc|public|scripts|templates
```

Notice that it gets all indirectly dependencies as well, and it keeps version value if there were a gopmfile exists already.

More information about how to write versions, please see [gopmfile](gopmfile.md).

## Options

- `--tags`: apply build tags when list dependencies.
- `--verbose, -v`: show process details.