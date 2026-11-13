
| **Command**                                | **Description**                                              |
| ------------------------------------------ | ------------------------------------------------------------ |
| `grep <pattern> <file>`                    | Display lines matching a pattern in a file.                  |
| `grep -i <pattern> <file>`                 | Display lines matching a pattern, ignoring case.             |
| `grep -v <pattern> <file>`                 | Display lines that do not match a pattern.                   |
| `egrep "<pattern1>\|<pattern2>" <file>`    | Display lines matching either pattern in a file.             |
| `egrep -i "<pattern1>\|<pattern2>" <file>` | Display lines matching either pattern, ignoring case.        |
| `wc -l <file>`                             | Count the lines in a file.                                   |
| `sort <file>`                              | Sort file lines alphabetically.                              |
| `sort -r <file>`                           | Sort file lines in reverse alphabetical order.               |
| `sort -u <file>`                           | Sort lines and remove duplicates.                            |
| `sed 's/<old>/<new>/g' <file>`             | Replace all occurrences of a pattern in each line.           |
| `sed '1d' <file>`                          | Remove the first line from the output.                       |
| `sed '1,10d' <file>`                       | Remove the first ten lines from the output.                  |
| `awk '{print $1,$2,$3}' <file>`            | Display the first three whitespace-separated fields.         |
| `awk -F: '{print $1,$2,$3}' <file>`        | Display fields 1, 2, and 3 using `:` as the field separator. |
| `history`                                  | Display commands recorded in shell history.                  |
| `!!`                                       | Execute the previous command again.                          |
| `!<number>`                                | Execute a command using its history number.                  |
| `history \| more`                          | Display command history one page at a time.                  |
| `history \| grep <pattern>`                | Search command history for a pattern.                        |
| `history -c`                               | Clear the current shell's in-memory history list.            |
