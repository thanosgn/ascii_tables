# cli-tables

Create a pretty looking ascii table.

## Installation (using pip):
`cli_tables` is offered as a python package from pypi.
You can install it with
```bash
pip install cli_tables
```

Or download and use it as a standalone command line utility.

## Usage (from python):
```python
from cli_tables.cli_tables import *
print_table([['Col 1', 'Col 2', 'Col 3', 'Col 4'],['v11', 'v12', 'v13', 'v14'],['v21', 'v22', 'v23', 'v24']])
```
```
+-------+-------+-------+-------+
| Col 1 | Col 2 | Col 3 | Col 4 |
+-------+-------+-------+-------+
|  v11  |  v12  |  v13  |  v14  |
+-------+-------+-------+-------+
|  v21  |  v22  |  v23  |  v24  |
+-------+-------+-------+-------+
```
```python
print_table([['Col 1', 'Col 2', 'Col 3', 'Col 4'],['v11', 'v12', 'v13', 'v14'],['v21', 'v22', 'v23', 'v24']], double_hline = True)
```
```
+-------+-------+-------+-------+
| Col 1 | Col 2 | Col 3 | Col 4 |
+=======+=======+=======+=======+
|  v11  |  v12  |  v13  |  v14  |
+-------+-------+-------+-------+
|  v21  |  v22  |  v23  |  v24  |
+-------+-------+-------+-------+
```
## Usage (command line):
```bash
python cli_tables.py [options] < input_file.txt
```

Where `input_file.txt` contains your input separated by (any amount of) tabs or 4/8/.. spaces and new-line characters and the output table is printed on the terminal.

## Usage (gui):
```bash
python gui.py
```

## Example:
### Input:
```
Col 1	Col 2	Col 3	Col 4
Val1	Val2	Val3	Val4
Val11	Val22	Val33	Val44
Vala	Valb	Valc	Vald
```
### Output (-h option):
```
+-------+-------+-------+-------+
| Col 1 | Col 2 | Col 3 | Col 4 |
+=======+=======+=======+=======+
| Val1  | Val2  | Val3  | Val4  |
+-------+-------+-------+-------+
| Val11 | Val22 | Val33 | Val44 |
+-------+-------+-------+-------+
| Vala  | Valb  | Valc  | Vald  |
+-------+-------+-------+-------+
```

The input in the command line execution can have an arbitrary amount of tabs (or 4/8/.. spaces) separating the values. For example either one of the following inputs will output the same result:
### Inputs:
```
input_size	algorithmA	algorithmB	algorithmC	algorithmD
1	206.4 sec.	206.4 sec.	0.02 sec.	0.02 sec.
4	900 sec.	431.1 sec.	0.08 sec.	0.062 sec.
250	-	80 min.	2.27 sec.	1.305 sec.
1000	-	-	8.77 sec.	4.086 sec.
5000	-	-	33.53 sec.	16.80 sec.
10000	-	-	85.4 sec.	47.18 sec.
```
or
```
input_size	algorithmA	algorithmB	algorithmC	algorithmD
1			206.4 sec.	206.4 sec.	0.02 sec.	0.02 sec.
4			900 sec.	431.1 sec.	0.08 sec.	0.062 sec.
250			-			80 min.		2.27 sec.	1.305 sec.
1000		-			-			8.77 sec.	4.086 sec.
5000		-			-			33.53 sec.	16.80 sec.
10000		-			-			85.4 sec.	47.18 sec.
```
### Output (-h and -v options):
```
+------------+------------+------------+------------+------------+
| input_size ‖ algorithmA | algorithmB | algorithmC | algorithmD |
+============+============+============+============+============+
|     1      ‖ 206.4 sec. | 206.4 sec. | 0.02 sec.  | 0.02 sec.  |
+------------+------------+------------+------------+------------+
|     4      ‖  900 sec.  | 431.1 sec. | 0.08 sec.  | 0.062 sec. |
+------------+------------+------------+------------+------------+
|    250     ‖     -      |  80 min.   | 2.27 sec.  | 1.305 sec. |
+------------+------------+------------+------------+------------+
|    1000    ‖     -      |     -      | 8.77 sec.  | 4.086 sec. |
+------------+------------+------------+------------+------------+
|    5000    ‖     -      |     -      | 33.53 sec. | 16.80 sec. |
+------------+------------+------------+------------+------------+
|   10000    ‖     -      |     -      | 85.4 sec.  | 47.18 sec. |
+------------+------------+------------+------------+------------+

```

### Options:
  1. `-h` double horizontal line after first row. (Uses '=' character)
  2. `-v` double vertical line after first column. (Uses '‖' unicode character)
