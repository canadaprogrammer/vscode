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
