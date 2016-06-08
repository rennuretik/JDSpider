About
====
    This is a simple spider that can help get prices sepecific items and store
    the them in an EXCEL file. If the price has been changed, then the program
    would automatically send an e-mail to notify the user.

Requirement
====
    :-Python2.7-:
    :-openpyxl-: $pip install openpyxl

Usage
====
    1. Create a new file named "item_list.txt" and fill it with the item you care about.
       One item per line;
       A simicolon(with a whitespace on its right side) sperates the item name on the right side and item website on the right side
       One example is showed below:
'''
DUNU 2000 Gold; http://item.jd.com/1118888.html
'''

    2. Create a new file named "config.txt" with infomation listed below:
'''
{
    "data": {
        "items": "item_list.txt",
        "excel_file": "prices.xlsx",
        "url_prefix": "http://p.3.cn/prices/mgets?",
        "pduid": "800XXXX08"
    },


    "time": {
        "refresh": 1200,
        "exit": 2
    },

    "e-mail": {
        "from_addr": "user@host.com",
        "host": "smtp.host.com",
        "port": 25,
        "password": "password",
        "to_addr": [
            "receiver@host.com"
            ],
        "subject": "Price changed detected from JDSpider",
        "timeout": 2
    }
}
'''
        items: File that stores the item information
        excel_file: Name of excel which collects the data
        pduid: Value of the COOKIE named __jdu from www.jd.com

        refresh: Time interval of two access in second

        from_addr: E-mail address of the sender
        host: SMTP host of the sender
        port: SMTP port
        password: Password of sender's e-mail
        to_addr: E-mail address of the receiver
        subject: Subject of the E-mail to be sent
        timeout: Time wait for the server to response

    3. $python JDSpider.py