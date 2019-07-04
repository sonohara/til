## gopls
https://github.com/golang/go/wiki/gopls

> `gopls` (pronounced: "go please") is an implementation of the Language Server Protocol (LSP) server for Go.

### install
```sh
go get golang.org/x/tools/gopls@latest
```

### vscode
```
"go.useLanguageServer": true,
"[go]": {
    "editor.snippetSuggestions": "none",
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
        "source.organizeImports": true
    }
},
"gopls": {
    "usePlaceholders": true // add parameter placeholders when completing a function
},
"files.eol": "\n", // formatting only supports LF line endings
```

### 参考
- [Golang開発環境を作成する(module対応) - Ubuntu16.04/VSCode](https://qiita.com/ochipin/items/cae787d75ae91247c722)