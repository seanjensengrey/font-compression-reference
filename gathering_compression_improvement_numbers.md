# Introduction #

One can easily gather the WOFF 2.0 compression improvement numbers for a given font collection in a few easy steps.

# Details #

**Download the reference codebase**
See the [Repository Checkout](https://code.google.com/p/font-compression-reference/source/checkout) page to clone the repository
```
$ git clone https://code.google.com/p/font-compression-reference/ 
```

**Build the project**
```
$ cd font-compression-reference/woff2
$ make clean all
```

**Run the tool over a given font**
```
$ ./woff2_compress MyFont.ttf
```

**Run the tool over a given font collection**
```
# Change to point to your fonts directory as needed
ttfs=$(find . -name '*.ttf')

# Create .woff2 versions of your ttf files
for f in $ttfs; do ./woff2_compress $f || { echo "Fail on $f"; exit 1; }; done

# Create a simple csv of { filename, ttf size, woff2 size }
rm -f ttf_to_woff2.csv
for f in $ttfs; do echo "${f##*/}, $(du -b $f | awk '{print$1}'),$(du -b ${f%.ttf}.woff2 | awk '{print$1}')" >> ttf_to_woff2.csv; done
```

**Analyze**

Then upload the resulting CSV file (`ttf_to_woff2.csv`) to Google Docs or similar.

For an example, see [WOFF 2.0 Compression Results for Google Fonts](https://docs.google.com/a/google.com/spreadsheet/ccc?key=0AvcH1ZzSrGMGdGl6MGRhdVRzYjN3T1NZSTBLM0ZUMnc)