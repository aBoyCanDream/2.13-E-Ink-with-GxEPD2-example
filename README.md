# 2.13-E-Ink-with-GxEPD2-example
Set up for using 2.13" "MH-ET LIVE" branded E-ink Displays with GxEPD2. It looks like the BW display uses the SSD1680 chip and the color uses another.

To use this sketch, make sure you have GxEPD2 installed. on Arduino IDE v2.2.1, you can do this in Library Manager. On older IDE, just download the library @ https://github.com/ZinggJM/GxEPD2 and put folder in your "/Arduino/libraries" folder.

On sketch, look for these lines to set your board:

// Use this for 3 color 2.13" "MH-ET LIVE" branded display. Set your own pins (these are what I used for my ESP32 S3 set up)
GxEPD2_3C<GxEPD2_213c, GxEPD2_213c::HEIGHT> display(GxEPD2_213c(/*CS=15*/ 38, /*DC=*/48, /*RST=*/47, /*BUSY=*/21)); // GDEW0213Z16
// Or comment above and uncomment below to use BW display:
//GxEPD2_BW<GxEPD2_213_GDEY0213B74, GxEPD2_213_GDEY0213B74::HEIGHT> display(GxEPD2_213_GDEY0213B74(/*CS=D8*/ 38, /*DC=D3*/ 48, /*RST=D4*/ 47, /*BUSY=D2*/ 21)); // GDEY0213B74 122x250, SSD1680, (FPC-A002 20.04.08)

Don't forget to set your own pins.

If you haven't bought the board yet, my 2 cents: Don't buy the three color if you plan on doing any regular updates. The 30 second refresh rate is excruciatingly slow and it barely handles partial refreshes. The BW version is more usable and the partial refresh works great.
