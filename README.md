I've created this repo to save me the time for googling up Linux Commands.
I am also adding some necessary code snippets for [Google Colab](https://colab.research.google.com/)

## Compress and Decompress Files and Directories

- Compress single file:


~~~
    zip zipfilewithoutext file 
~~~
This will create a file named `zipfilewithoutext.zip`

- Compress multiple file:

~~~
zip zipfilename file1 file2 file3 
~~~
- Compress files with certain extensions.
~~~
zip -R foo '*.ext1' '*.ext2' '*.ext3' '*.ext4'
~~~
- Decompress a zip file:
~~~
unzip zipfilewithoutext.zip
~~~
- Decompress a zip file and then delete the original zip file
~~~
find . -depth -name '*.zip' -execdir unzip -n {} \; -delete
~~~

## Find directories and files with names and contents

- Find directory with a name:
~~~
find . -type d -name "{FOLDER_NAME}"
~~~ 
- Find file with a certain string:
~~~
grep -iRl "your-text-to-find" ./
~~~
Here, 
~~~
-i - ignore text case
-R - recursively search files in subdirectories.
-l - show file names instead of file contents portions.
-n - show the line number.
-w - match the whole word.
~~~

## Google Colab

- Mounting Google Drive:
~~~
from google.colab import drive
drive.mount('/content/gdrive/')
~~~
- Change Directory in python:
~~~
import os
os.chdir('dirname')
~~~
## Running python scripts and commands

- Running a script with nohup in background with output and errors redirection to a file
~~~
nohup python {SCRIPTNAME} > {OUTPUT_FILENAME} 2>&1 &
~~~
- Observe output of a command after a fixed time period:
~~~
watch -n time_in_sec terminal_command -u username
~~~
## File/Directory Characteristics
- Get number of files in the current directory:
~~~
ls -l | wc -l
~~~