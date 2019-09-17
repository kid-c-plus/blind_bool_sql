-------- Boolean-Based Blind SQL Injector --------

Usage: python3 sql_inject.py [opts] root_url conditional

root_url    : the root url to attack, up to the = operand for the vulnerable URL parameter
conditional : command to execute on the SQL server and exfiltrate back (e.g. user())

The attack URL is constructed as such, assuming root_url = "vuln.com/hack.php?badvar=" and conditional = "database()", where <substr_i> is the index of the value in the conditional being exfiltrated and <char> is the character it's currently being tested against:

    vuln.com/hack.php?badvar=IF(SUBSTRING(database(),<substr_i>,1)="<char>",1,0)

The character list that the script iterates <char> through can be configured in the charlist.txt file.

opts:
    -h  : display this help page and exit
    -v  : verbose
    -p  : use BeautifulSoup to parse out the text from the HTML responses  and use that for boolean evaluation
    -s [sleep_val]  : sleep for sleep_val seconds between requests (floating point, default 0.1, can be zero)
