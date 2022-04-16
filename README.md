[![Twitter Follow](https://img.shields.io/twitter/follow/0xbadad?style=social)](https://twitter.com/0xbadad)
# subdirectories-discover wordlist
Perfect wordlist to discover directories and files on target site with tools like ffuf.
- It was collected by parsing Alexa top-million sites for **.DS_Store** files (https://en.wikipedia.org/wiki/.DS_Store), extracting all the found files, and then extracting found file and directory names from around 300k real websites.
- Then sorted by probability and removed strings with one occurrence.
- resulted file you can download is below. Happy Hunting!
# usage example
```
echo trustedshops.com | subfinder -silent | aquatone;
cat ~/aquatone_urls.txt | feroxbuster --stdin --extract-links --silent -s 200 -x php -r -BEg -w <(curl -fskSL bit.ly/dsstorewordlist)
```
```
ffuf -w <(curl -fskSL bit.ly/dsstorewordlist) -u https://analytics.trustwalletapp.com/FUZZ -r
```
List url: https://raw.githubusercontent.com/aels/subdirectories-discover/main/dsstorewordlist.txt

You don't need to download it every time and store somewhere. You can use command `<(curl -fskSL bit.ly/dsstorewordlist)` instead of local path to file in all tools you are using.
Personally I recomend to use it with tools like
- **ffuf** https://github.com/ffuf/ffuf
- **feroxbuster** https://github.com/epi052/feroxbuster
