Relative Luminance Kata
=======================

This coding kata has several steps:

* Calculation of the relative luminance for a given RGB color code
* Calculation of the contrast ratio for two RGB color codes
* Calculation of the minimum contrast ratio for large and regular text
* Input of CMYK color codes instead of RGB color codes

Relative Luminance
------------------

Source: http://www.w3.org/TR/2008/REC-WCAG20-20081211/#relativeluminancedef

The relative brightness of any point in a colorspace, normalized to 0 for darkest black and 1 for lightest white.
 
For the sRGB colorspace, the relative luminance of a color is defined as:
  
	L = 0.2126 * R + 0.7152 * G + 0.0722 * B
 
where R, G and B are defined as:
 
	if RsRGB <= 0.03928 then R = RsRGB/12.92 else R = ((RsRGB+0.055)/1.055) ^ 2.4
	if GsRGB <= 0.03928 then G = GsRGB/12.92 else G = ((GsRGB+0.055)/1.055) ^ 2.4
	if BsRGB <= 0.03928 then B = BsRGB/12.92 else B = ((BsRGB+0.055)/1.055) ^ 2.4
 
and RsRGB, GsRGB, and BsRGB are defined as:
 
	RsRGB = R8bit/255
	GsRGB = G8bit/255
	BsRGB = B8bit/255
 
The "^" character is the exponentiation operator.

Contrast Ratio
--------------

Source: http://www.w3.org/TR/WCAG20/#contrast-ratiodef

Contrast ratios can range from 1 to 21 (commonly written 1:1 to 21:1). They are defined as:
  
	(L1 + 0.05) / (L2 + 0.05)
 
, where L1 is the relative luminance of the lighter of the colors, and L2 is the relative luminance of the darker of the colors.

Minimum Contrast Ratio
----------------------

Source: http://www.w3.org/TR/WCAG20/#visual-audio-contrast-contrast
   
The latest accessibility guidelines require that text (and images of text) provide adequate contrast for people who have visual impairments. Contrast is measured using a formula that gives a ratio ranging from 1:1 (no contrast, e.g., black text on a black background) to 21:1 (maximum contrast, e.g., black text on a white background).
 
Using this formula, the requirements are:
 
	3:1 - minimum contrast for "large scale" text (18 pt or 14 pt bold, or larger) under WCAG 2.0 1.4.3 (Level AA)
	4.5:1 - minimum contrast for regular sized text under WCAG 2.0 1.4.3 (Level AA)
	7:1 - "enhanced" contrast for regular sized text under WCAG 2.0 1.4.6 (Level AAA)

Eingabe von CMYK-Werten
Formel: http://www.rapidtables.com/convert/color/cmyk-to-rgb.htm

CMYK to RGB conversion formula
------------------------------
 
The R,G,B values are given in the range of 0..255.
 
The red (R) color is calculated from the cyan (C) and black (K) colors:

	R = 255 × (1-C) × (1-K)
 
The green color (G) is calculated from the magenta (M) and black (K) colors:

	G = 255 × (1-M) × (1-K)
 
The blue color (B) is calculated from the yellow (Y) and black (K) colors:

	B = 255 × (1-Y) × (1-K)
