# Code Structure, Comment & Formatting
## Comments
### What Things Make Bad Comments
1. Redundant Information
2. Divider / Block Markers
3. Misleading Comments
4. Comments-Out Code

### What Things Make Good Comments
1. Legal Information
2. Explanation which can't be replaced by good naming
3. Warning
4. Todo Notes

## Formatting
Code formatting improves readability & transports Meaning. That has 2 kinds of formatting: Vertical (Space between lines and Grouping of codes) and Horizontal (Identation, Space between Code, and Line width)
### Vertical Formatting
1. Code should be readable like an essay - top to bottom without too many "jumps"
   * Consider splitting files with multiple concepts (e.g. classes) into multiple files
   * Different concepts ("areas") should be separated by spacing
   * Similar concepts ("areas") should not be separated by spacing
   * Related concepts should be kept close to each other
### Horizontal Formatting
1. Lines of code should be readable without scrolling - avoid very long "sentences"
   * Use indentation (tab/space/enter) - even if not required technically
   * Break long statements into multiple shorter ones (define to another variable)
   * Use clear but not unreadably long names
  
## Exercise Code Structure, Comment & Formatting
```Phyton
# (c) Maximilian Schwarzmüller / Academind GmbH

from os import path, makedirs
from pathlib import Path

class DiskStorage:
    def __init__(self, directory_name):
        self.storage_directory = directory_name

    def get_directory_path(self):
        return Path(self.storage_directory)

    def create_directory(self):
        if (not path.exists(self.get_directory_path())):
            makedirs(self.storage_directory)

    # Warning: Directory must exist in advance
    def insert_file(self, file_name, content):
        file_path = self.get_directory_path() / file_name
        file = open(file_path, 'w')
        file.write(content)
        file.close()
        # Todo: Add proper error handling


log_storage = DiskStorage('logs')

log_storage.create_directory()
log_storage.insert_file('test.txt', 'Test')
```
