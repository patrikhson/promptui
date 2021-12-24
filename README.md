# addressbook
## Description
Synk addresses between internet and local Sqlite db

Specifically this program synks between Ratsit web and local sqlite db.

Commands:
```
$ ./addressbook [-first FIRST] [-last LAST] [-city CITY] [-ssn SSN]
```
Fetches from database record where one or more of the search items are true. Substring works for for example SSN where 1965 matches every person being born in 1965.
```
$ ./addressbook -id ID
```
Fetches record with id ID
```
$ ./addressbook -find -id ID
```
Fetches record from internet with id ID
```
$ ./addressbook -find [-first FIRST] [-last LAST] [-city CITY] [-ssn SSN]
```
Fetches from internet record where one or more of the search items are true. Substring works for for example SSN where 1965 matches every person being born in 1965. If more than one record matches, a list with the first 10 records is displayed and one can select which one of the records one want to display.
```
$ ./addressbook -find -add [-first FIRST] [-last LAST] [-city CITY] [-ssn SSN]
```
Like a fetch from the internet, but adds record to the database,
```
$ ./addressbook -diff [-id ID] [-first FIRST] [-last LAST] [-city CITY] [-ssn SSN]
```
Checks records in the local database with data on the internet. Checks records that matches the search expression, or all records if not expression is given.
```
$ ./addressbook -add -diff [-id ID] [-first FIRST] [-last LAST] [-city CITY] [-ssn SSN]
```
Checks records in the local database with data on the internet, and updates the data in the local database. Checks records that matches the search expression, or all records if not expression is given.

## Example

```
$ ./addressbook -find -first patrik -last fältström
Found 2 records
0: 19650510 Patrik H:Son Fältström, Kullamöllevägen 276-13, 27571 Lövestad
1: 19700624 Patrik Axel Fältström, Tunnlandsvägen 14, 61234 Finspång
Choose person: 0
ID: TJYDz-DckaOKic-DH4lUqN7Kbqe6wOrZpKkErmJYrDQ
Name: Patrik H:Son Fältström
Address: Kullamöllevägen 276-13
Postal address: 275 71 Lövestad
Birth date: 1965-05-10
Telephone: 
$ ./addressbook -find -id TJYDz-DckaOKic-DH4lUqN7Kbqe6wOrZpKkErmJYrDQ
ID: TJYDz-DckaOKic-DH4lUqN7Kbqe6wOrZpKkErmJYrDQ
Name: Patrik H:Son Fältström
Address: Kullamöllevägen 276-13
Postal address: 275 71 Lövestad
Birth date: 1965-05-10
Telephone: 
$ ./addressbook -first patrik -last fältström
1965-05-10, Patrik H:Son Fältström, Kullamöllevägen 276-13, 275 71 Lövestad, 
$ 
```
