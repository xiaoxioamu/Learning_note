### 如何向 argparser 传递列表参数
[python - How can I pass a list as a command-line argument with argparse? - Stack Overflow](https://stackoverflow.com/questions/15753701/how-can-i-pass-a-list-as-a-command-line-argument-with-argparse)

Use the nargs option or the 'append' setting of the action option (depending on how you want the user interface to behave).

**nargs**

parser.add_argument('-l','--list', nargs='+', help='<Required> Set flag', required=True)

`python arg.py -l 1234 2345 3456 4567`


nargs='+' takes 1 or more arguments, nargs='*' takes zero or more.

**append**

parser.add_argument('-l','--list', action='append', help='<Required> Set flag', required=True)
Use like:
`python arg.py -l 1234 -l 2345 -l 3456 -l 4567`

With append you provide the option multiple times to build up the list.

Don't use type=list!!! - There is probably no situation where you would want to use type=list with argparse. Ever.

