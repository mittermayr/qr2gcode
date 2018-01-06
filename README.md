# qr2gcode

Generate a QR code and convert to executable Gcode for CNC machines

## Requirements

`gem install rqrcode`

## Syntax

`ruby qr2gcode.rb 12345`

This will generate a QR code on the fly, and then convert the data into a GCODE file by using each pixel of the QR code as a drilling/milling point. The file will be named `qrcode.ngc` and placed in the current directory.

### Vertical refinement

There is an option to *vertically refine*, which simply means that after going through every single row of the code, the mill will then restart at the beginning and go through every column of the print to have lines go through more smoothly vertically as well as horizontally.

### Usage tips

For best results, make sure there is very high contrast between the milled paths and the untouched surrounding material. QR code readers can handle a lot of errors and poorly milled individual pixels, but they need that contrast to work well.

### Possible adjustments and settings

* You can turn off the border: `add_border=false`
* You can adjust all coordinates: `x_home, y_home, spacing, feed_rate, z_depth, z_hover, z_safe`
* You can adjust the QR code parameters, like error-level and other things
