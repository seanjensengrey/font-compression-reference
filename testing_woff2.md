# Introduction #

The WOFF 2.0 reference implementation can be tested end-to-end using Chrome M36+ (beta at time of writing).

# Details #

## Google Fonts (Directory) ##

Support for WOFF 2.0 has been enabled in the dynamic serving path.  Specifically, for the
[&text=](https://developers.google.com/fonts/docs/getting_started#Optimizing_Requests) requests which are heavily used by the directory to show dynamic font previews.

Thus, to preview the fonts served as WOFF 2.0, access the Google Fonts directory:

http://www.google.com/fonts

And then view the fonts via the Choose: Word, Sentence and Paragraph tabs.

To confirm, you can use the Chrome 'Inspect Element' Network tab, to view all of the font requests.  Notice the "font/woff2" requests!

## Google Fonts (Early Access) ##

The Early Access fonts are also being served as WOFF 2.0:

http://www.google.com/fonts/earlyaccess

To view the fonts served as WOFF 2.0, you will need to create a test page using one of the Early Access fonts.  See the corresponding link/example for each font on the Early Access page.

## Converting Fonts to WOFF 2.0 ##

The Font Compression Reference tool converts fonts into WOFF 2.0.  Thus, you can use the tool to convert your own fonts and test them.

To run the conversion tool, see the following
[instructions](gathering_compression_improvement_numbers.md)

In addition to gathering compression improvement results, the tool saves the WOFF 2.0 files as .woff2, which you can then use in test pages.