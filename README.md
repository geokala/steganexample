# Usage
The working example is currently process_bmp
It only works with at least 24 bits per pixel (e.g. RGB or alpha+RGB). On anything else it'll likely blow up.
Rather than parsing images by hand, it would make sense in a non-example program to use, e.g. pillow for image parsing (or another library for other media).

Run:
> ./process_bmp check cc.bmp
This will show how many bytes the cc.bmp image can store.

> ./process_bmp store cc.bmp "My test message in utf-8"
This will store the message in the modified file: cc.bmp.mod.bmp

> ./process_bmp retrieve cc.bmp.mod.bmp
This will print the message stored in the given bitmap.
It'll probably crash if run on an unmodified bitmap.

# Notes

Image (cc.png) retrieved from https://mirrors.creativecommons.org/presskit/icons/cc.png and used under Creative Commons.
Exported as bmp using GNU Image Manipulation Program.

PNG file format details obtained from https://en.wikipedia.org/wiki/Portable_Network_Graphics
BMP file format details obtained from https://en.wikipedia.org/wiki/BMP_file_format

Note that PNG is only partially implemented as the complexity probably doesn't lend it towards a starting example quite so much as a bitmap does.
Other formats are of course feasible- anything lossless should be relatively straight-forward, but anything with lossy compression would be... interesting (though maybe not impossible).

Another way of working with PNGs would be to add a custom header containing the data (obfuscated or otherwise).
Standard image viewing programs wouldn't show the data, but it'd still be visible to any program that supported that header.
However, this method would be rather more obvious when, e.g. viewing the file with a hex editor, so would depend on the purpose and the desire for deniability.
