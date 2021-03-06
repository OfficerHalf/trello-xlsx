### NOTE
I spent two hours writing this only to find out there's a Chrome extension that already does it, and better. See here: [Export for Trello](https://chrome.google.com/webstore/detail/export-for-trello/nhdelomnagopgaealggpgojkhcafhnin?hl=en-US)

Trello doesn't allow you to export your board to CSV or XSLX if you don't pay for their "business class" model - only JSON. I think that's pretty lame, so I wrote this little python script to convert the JSON to an XLSX file.

It spits out a XLSX workbook where each sheet is one of the lists on the given Trello board. The output is pretty ugly, but it's a starting point.

### Requirements
Python 3.x

[XlsxWriter](https://pypi.python.org/pypi/XlsxWriter)  
`pip install XlsxWriter`

### Usage
Basic usage:  
`python3 trello-xlsx.py infile.json outfile.xlsx`

Advanced usage:  
`python3 trello-xlsx.py infile.json outfile.xlsx -l -i --add-empty`

### Options
| Short | Long | Description |
| --- | --- | --- |
| -h | --help | Print help. |
| -v | --verbose | Lots of output. This is just for debugging, really. |
| -l | --labels | By default, the script takes only the names of the labels for each card. With this option, it takes all fields. |
| -i | --info | Add two rows to each sheet with info about the list. |
| N/A | --add-empty | By default, empty lists are ignored. With this flag, they are included. |

### Future Work
I'm working on a number of default filters to make the output prettier by excluding unnecessary columns (IDs etc.) and ordering the columns consistently.