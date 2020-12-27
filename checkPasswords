#!/usr/bin/env python3

__author__ = 'nixCraft'

import sys
import requests
import hashlib

check = False


def checkFunction(myPassword):

    check = False
    sha1password = hashlib.sha1((myPassword).encode('utf-8')).hexdigest().upper()
    first5 = sha1password[0:5]
    url = "https://api.pwnedpasswords.com/range/" + str(first5)
    r = requests.get(url)
    passwords = r.text.split("\r\n")

    for password in passwords:
        if sha1password[5:] in password: 
            temp = password.split(":")
            print(myPassword + " was found " + temp[1]  + " times. You should probably change your password!" )
            check = True
    if (not check):
        print(myPassword + " was NOT found. Carry on !")   

total = len(sys.argv)
for x in range(total-1):
     checkFunction(str(sys.argv[x+1]))


     


