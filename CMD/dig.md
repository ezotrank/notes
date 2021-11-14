# dig

**Show TXT records in domain**

`dig -t txt +short  example.com @1.1.1.1`

**Show hide TXT records, for ACME challange** 

`dig +short txt _acme-challenge.test3.sg1.example.com @1.1.1.1`

**Show NS records**

`dig +short NS example.com`

**Show traces**

`dig google.com +trace`


### Links

[DNS Basics and Building Simple DNS Server in Go](https://medium.com/@openmohan/dns-basics-and-building-simple-dns-server-in-go-6cb8e1cfe461)