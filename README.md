# Overview
This project was created to convert Box Notes to Microsoft Word Documents.
It can handle both the 'old' and 'new' Box Note formats. It uses the adjunct custom-reference.docx file to inform the pypandoc library regarding the reference-doc to use (e.g. to add borders to tables).

# Usage
Point to a boxnote to be converted:

```sh
boxnote2docx -b path/to/boxnote
```

Specify folder to place Word doc(s) (recommended):

```sh
boxnote2docx -b path/to/boxnote -d directory-to-place-converted-docx
```

Example of a batch run:

```sh
find /path-to/boxnotes -type f -name '*.boxnote' -print0 |
while IFS= read -r -d '' file; do
    ./boxnote2docx -b "$file" -d /path-to/converted-dir/ 2>&1
done | tee boxnote2docx.log
```

# Installation
Create a virtual environment and install the required modules
```
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt 
```

If you do not have pandoc installed, it can be installed via Brew.
