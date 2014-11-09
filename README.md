SHSDeskInterface
================
##// Disclaimer
This modified set of Source Han Sans is made for OS X &amp; iOS's GUI font purposes only.

These fonts should be installed **via sudo privileges** to the system font folder:
<pre><code>chown root:wheel "/System/Library/Fonts/FONTFILENAME.ttc"
chmod 644 "/System/Library/Fonts/FONTFILENAME.ttc"</code></pre>

These fonts are **user-inaccessible hidden fonts** in every font menu in every app; Only **CTPresetFallbacks.plist** and **DefaultFontFallbacks.plist** could let them work possible, with **STHeiti's complete removal** required.

P.S.: Specifically modified font fallback files could let this fontset work better.

You may want to install official SHS build again for any other usages you want:<br>
https://github.com/adobe-fonts/source-han-sans/tree/release

##// Installation

You should visit this website: https://github.com/othercat/CJKFontScript , download `install_SHS-DeskInterfaceOnly.sh`, and run `sudo bash install_SHS-DeskInterfaceOnly.sh` in Terminal. Please close all other applications and finish all of your other pending Terminal process before running this installer script (there will be an automatic reboot with prompt).

##// Parameters Modified from SHS (excl. PostScript name)

We added and modified some parameters among all of those "features.otc.???" files.<br>
(We only talk about Langage-Specific Releases, not Region-Specific Releases.)

Step 1: Add following info before VHEA table:
<pre><code>table hhea {
  Ascender 807;
  Descender -192;
  LineGap 30;
} hhea;</code></pre>
Step 2: Find 
<pre><code>table OS/2 {
  TypoAscender 880;
  TypoDescender -120;
  TypoLineGap 500;</code></pre>
Change into:
<pre><code>table OS/2 {
  Ascender 807;
  Descender -192;
  TypoLineGap 0;</code></pre>

Those steps above could let the SHS display correctly as System's CJK GUI font while you are doing CJK filename's renaming:

![image](https://cloud.githubusercontent.com/assets/3164826/4935104/89d617d0-65a8-11e4-9c3b-8a220cc09ef4.png)

And it shows the same display lineHeight as STHeiti in iMessages.

That's all.

[EOF]
