# Note related to vscode use

## Turn 4 spaces indents in all files in vscode to 2 spaces

1. Open file search
2. Turn on Regular Expressions
3. Enter a regular expression in the search field

- `((( {2})(?: {2}))(\b|(?!=[,'";\.:\*\\\/\{\}\[\]\(\)])))`

4. Enter `$3` in the replace field

## Turn 2 spaces indents in all files in vscode to 4 spaces

1. Open file search
2. Turn on Regular Expressions
3. Enter a regular expression in the search field

- `((( {2}))(\b|(?!=[,'";\.:\*\\\/\{\}\[\]\(\)])))`

4. Enter `$3$3` in the replace field

## Modify Themes

1. `ctrl + shift + p` and searching for `Preferences: Open Settings (JSON)`
2. Check the inspection and identification by typing `Developer: Inspect Editor Tokens and Scopes` from the Command Palette(`ctrl + shift + p`).
3. Type code in `settings.json`.

- ```json
  "editor.tokenColorCustomizations": {
    "[One Dark Pro Darker]": {
      "textMateRules": [
        {
          "scope": "variable.other.constant",
          "settings": {
            "foreground": "#e0a66c",
            "fontStyle": "bold"
          }
        },
        {
          "scope": "variable.other.object",
          "settings": {
            "foreground": "#e5ce7b",
          }
        },
        {
          "scope": "variable",
          "settings": {
            "foreground": "#c7e57b",
          }
        }
      ]
    }
  },
  "editor.semanticTokenColorCustomizations": {
    "[One Dark Pro Darker]": {
      "rules": {
        "parameter": "#e07f6c",
      }
    }
  }
  ```
