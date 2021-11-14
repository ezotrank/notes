# Problems

**ld: symbol(s) not found for architecture x86_64**

```
brew uninstall binutils
pyenv install
```

**pycurl and ssl problem**

`LDFLAGS="-L/usr/local/opt/openssl/lib" CPPFLAGS="-I/usr/local/opt/openssl/include" pyenv exec pip install --compile --install-option="--with-openssl" pycurl`

**psycopg2 and ssl problem**

`LDFLAGS="-L/usr/local/opt/openssl/lib" CPPFLAGS="-I/usr/local/opt/openssl/include" pyenv exec pip install -r requirements.txt`


**modules/packages have invalid Python name**

[link](https://stackoverflow.com/a/50610630)

`touch conftest.py`