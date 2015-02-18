SourceHanSansUI
================

Formerly SHSDeskInterface.

##// Disclaimer
This modified set of Source Han Sans is made for OS X &amp; iOS's GUI font purposes only.

These fonts should be installed **via sudo privileges** to either the system font folder `/System/Library/Fonts/` or library font folder `/Library/Fonts/`:
<pre><code>chown root:wheel "/Library/Fonts/FONTFILENAME.ttc"
chmod 644 "/Library/Fonts/FONTFILENAME.ttc"</code></pre>

These fonts' post script names are hidden under OS X; Only **CTPresetFallbacks.plist** and **DefaultFontFallbacks.plist modified via those scripts provided from https://github.com/othercat/CJKFontScript** could let them work as GUI fonts in OS X Yosemite, with current STHeiti's **removal** recommended.

P.S.: Factorial font Plist files couldn't work with this font set.

You may want to install official SHS build again for any other usages you want:<br>
https://github.com/adobe-fonts/source-han-sans/tree/release

##// Installation

You should visit this website: https://github.com/othercat/CJKFontScript , download `install_SHS-UI.sh`, and run `sudo bash install_SHS-UI.sh` in Terminal. Please close all other applications and finish all of your other pending Terminal process before running this installer script (there will be an automatic reboot with prompt).

##// Parameters Modified from SHS (excl. PostScript name)

We added and modified some parameters among all of those "features.otc.???" files.<br>
(We only talk about Langage-Specific Releases, not Region-Specific Releases because nobody want to see glyph-blank-box while using these fonts.)

P.S.: Special thanks to **Kobayashi Ken (a.k.a. Ken Lunde, the programmer of Source Han Sans)** for his suggestion on pointing out which parameter should be modified and his tips on using AFDKO, otherwise I couldn't get this achieved. But we have to clear the LineGap and add its reasonable value up to the Ascender in order to deal with the following problem:

> OS X Yosemite has serious problem regarding its UILabel elements: they omit the lineGap data, cause display malfunction among multi-line filenames in Finder if the display font has lineGap data.

Step 1: Add following info before VHEA table:
<pre><code>table hhea {
  Ascender 1000;
  Descender -234;
  LineGap 0;
} hhea;</code></pre>
Step 2: Find 
<pre><code>table OS/2 {
  TypoAscender 880;
  TypoDescender -120;
  TypoLineGap 500;</code></pre>
Change into:
<pre><code>table OS/2 {
  TypoAscender 1000;
  TypoDescender -234;
  TypoLineGap 0;</code></pre>

Those steps above could let the SHS display correctly as System's CJK GUI font while you are doing CJK filename's renaming:

![image](https://cloud.githubusercontent.com/assets/3164826/5310999/bb4b5d26-7bfa-11e4-8c64-a047c7c0a53a.png)

And it shows the better display lineHeight than STHeiti in iMessages:

![image](https://cloud.githubusercontent.com/assets/3164826/5310910/d05232f0-7bf8-11e4-8482-adab07c07997.png)

And it shows multi-line filename well in Finder:
![image](https://cloud.githubusercontent.com/assets/3164826/5991332/a4c86508-a9a4-11e4-8f86-618af29368d3.png)

More screenshots (for both Traditional and Simplified Yosemite GUI):
http://1drv.ms/12r4uoc

That's all.

[EOF]
