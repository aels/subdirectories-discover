[![Twitter Follow](https://img.shields.io/twitter/follow/0xbadad?style=social)](https://twitter.com/0xbadad)
# subdirectories-discover wordlist
Perfect wordlist to discover directories and files on target site with tools like ffuf.
- It was collected by parsing Alexa top-million sites for **.DS_Store** files (https://en.wikipedia.org/wiki/.DS_Store), extracting all the found files, and then extracting found file and directory names from around 300k real websites.
- Then sorted by probability and removed strings with one occurency.
- resulted file you can download below. Happy Hunting!
# usage example
```
echo trustedshops.com | subfinder -silent | aquatone;
cat ~/aquatone_urls.txt | feroxbuster --stdin --extract-links --silent -s 200 -x php -r -BEg -w (wget -nv bit.ly/dsstorewordlist -O dsstorewordlist.txt 2>&1 | cut -d\" -f2);
```
```
curl -fsSL bit.ly/dsstorewordlist > /tmp/dsstorewordlist.txt;
ffuf -w /tmp/dsstorewordlist.txt -u https://analytics.trustwalletapp.com/FUZZ -r
```
