## Argparse
### What is it?
```
Parser for command-line options, arguments and subcommands.The argparse module makes it easy to write user-friendly command-line interfaces. 

When you run the "ls" command without any options, it will default displaying the
contents of the current directory

If you run "ls" on a different directory that you currently are in, you would type
"ls directory_name". The "directory_name" is a "positional argument", which means
that the program know what to do with the value. 

To get more information about a file we can use the "-l" switch.

The "-l" is knowns as an "optional argument"

If you want to display the help text of the ls command, you would type "ls --help"
```
### How to use?
We need to import the following:
```python
import argparse
parser = argparse.ArgumentParser()
parser.parse_args()
```
Even without the arguements being specified, executing this code with '--help' option gives us the only pre-coded messgae available.
```python
python program.py --help (or python program.py -h) 
usage: program.py [-h]

optional arguments:
  -h, --help  show this help message and exit
```

### Example
```python
import argparse
import sys

def main():
    parser = argparse.ArgumentParser()
    parser.add_argument('--x', type=float, default=1.0,
                        help='What is the first number?')
    parser.add_argument('--y', type=float, default=1.0,
                        help='What is the second number?')
    parser.add_argument('--operation', type=str, default='add',
                        help='What operation? Can choose add, sub, mul, or div')
    args = parser.parse_args()
    sys.stdout.write(str(calc(args)))
    
def calc(args):
    if args.operation == 'add':
        return args.x + args.y
    elif args.operation == 'sub':
        return args.x - args.y
    elif args.operation == 'mul':
        return args.x * args.y
    elif args.operation == 'div':
        return args.x / args.y

if __name__ == '__main__':
    main()
```
Now if we pass values for x and y and also specify the operation, we get the desired results
```python
python argparse_example.py --x=5 --y=3 --operation=mul
15.0
```
Instead, if we invoke the help option, we get
```python
python argparse_example.py -h
usage: argparse_example.py [-h] [--x X] [--y Y] [--operation OPERATION]

optional arguments:
  -h, --help            show this help message and exit
  --x X                 What is the first number?
  --y Y                 What is the second number?
  --operation OPERATION
                        What operation? Can choose add, sub, mul, or div
```

