-------- Boolean-Based Blind SQL Injector --------

Usage: python3 sql_inject.py [opts] root_url conditional

opts:
    -h  : display this help page and exit
    -v  : verbose
    -p  : use BeautifulSoup to parse out the text from the HTML responses  and use that for boolean evaluation
    -s [sleep_val]  : sleep for sleep_val seconds between requests (floating point, default 0.1, can be zero)
