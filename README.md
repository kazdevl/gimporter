# gimporter
gimporter is a tool for aliging imported-package list.
[![License](https://img.shields.io/github/license/kazdevl/gimporter)](/LICENSE)

## Installation
```zsh
$ go install github.com/kazdevl/gimporter/cmd/gimporter@latest
```

## Usage
If you have go file that has wrong order imported-packaged list, you can use this tool effectively.
```
## Before
package sample

import (
    "fmt"
    "log"

    "github.com/hoge"

    "my-original-package/hoge"

    "github.com/fuga"

    "my-original-package/hogehoge"
    "my-original-package/fuga"
)

## After
package sample

import (
    "fmt"
    "log"

    "github.com/fuga"
    "github.com/hoge"

    "my-original-package/fuga"
    "my-original-package/hoge"
    "my-original-package/hogehoge"
)
```