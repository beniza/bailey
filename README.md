# Bailey

Bailey is a fully customizable PEG based data parsing tool (primarily designed to parse dictionary data from plain text files)

## How to use Bailey

At the moment there are no executables available for using Bailey. We might release a `cli` later. You may still be able to use this utility by cloning this repo and then running it on your local system.

### Step 1ː Install dependencies
> $ python setup.py install

### Step 2ː Run Bailey
> $ python bailey/baily.py path/to/dictionary_plain_text_file

Running the above will generate two outputs. 1) a dictionary representation of all the valid entries (entries that matches the expression in the grammar) in the dictionary_plain_text_file 2) every invalid entries in the file will be stored inside a `error.log` file with the corresponding line numbers.

## Output
Bailey currently output data in Multi Dictionary Format (MDF) version 4.0. For more info please see the [description](lexical_entry.md) of entries in the MDF.

## Testing
To test the script, simply run

> $ python baily/baily.py

This should output a sample dictionary format.
