[![Twitter Follow](https://img.shields.io/twitter/follow/0xbadad?style=social)](https://twitter.com/0xbadad)
# subdirectories-discover wordlist
Perfect wordlist to discover directories and files on target site with tools like ffuf.
- It was collected by parsing Alexa top-million sites for **.DS_Store** files (https://en.wikipedia.org/wiki/.DS_Store), extracting all the found files, and then extracting found file and directory names from around 300k real websites.
- Then sorted by probability and removed strings with one occurency.
- resulted file you can download below. Happy Hunting!
# usage example
```
curl -fsSL bit.ly/dsstorewordlist > /tmp/dsstorewordlist.txt;
echo trustedshops.com | subfinder -silent | sed -e 's/^/https:\/\//' | feroxbuster --stdin --extract-links --silent -s 200 301 302 -r -w /tmp/dsstorewordlist.txt -BEg
```
```
curl -fsSL bit.ly/dsstorewordlist > /tmp/dsstorewordlist.txt;
ffuf -w /tmp/dsstorewordlist.txt -u https://analytics.trustwalletapp.com/FUZZ -r
```
