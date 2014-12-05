SHSDeskInterface
================
##// Disclaimer
This modified set of Source Han Sans is made for OS X &amp; iOS's GUI font purposes only.

These fonts should be installed **via sudo privileges** to either the system font folder `/System/Library/Fonts/` or library font folder `/Library/Fonts/`:
<pre><code>chown root:wheel "/Library/Fonts/FONTFILENAME.ttc"
chmod 644 "/Library/Fonts/FONTFILENAME.ttc"</code></pre>

These fonts are **user-inaccessible hidden fonts** in every font menu in every app; Only **CTPresetFallbacks.plist** and **DefaultFontFallbacks.plist** could let them work possible, with **STHeiti's complete removal** required.

P.S.: Specifically modified font fallback files could let this fontset work better.

You may want to install official SHS build again for any other usages you want:<br>
https://github.com/adobe-fonts/source-han-sans/tree/release

##// Installation

You should visit this website: https://github.com/othercat/CJKFontScript , download `install_SHS-DeskInterfaceOnly.sh`, and run `sudo bash install_SHS-DeskInterfaceOnly.sh` in Terminal. Please close all other applications and finish all of your other pending Terminal process before running this installer script (there will be an automatic reboot with prompt).

##// Parameters Modified from SHS (excl. PostScript name)

We added and modified some parameters among all of those "features.otc.???" files.<br>
(We only talk about Langage-Specific Releases, not Region-Specific Releases.)

P.S.: Special Thanks to Ken Lunde for technical support about using AFDKO, otherwise I couldn't get this achieved.

Step 1: Add following info before VHEA table:
<pre><code>table hhea {
  Ascender 880;
  Descender -120;
  LineGap 100;
} hhea;</code></pre>
Step 2: Find 
<pre><code>table OS/2 {
  TypoAscender 880;
  TypoDescender -120;
  TypoLineGap 500;</code></pre>
Change into:
<pre><code>table OS/2 {
  TypoAscender 880;
  TypoDescender -120;
  TypoLineGap 100;</code></pre>

Those steps above could let the SHS display correctly as System's CJK GUI font while you are doing CJK filename's renaming:

![image](https://cloud.githubusercontent.com/assets/3164826/5310999/bb4b5d26-7bfa-11e4-8c64-a047c7c0a53a.png)

And it shows the better display lineHeight than STHeiti in iMessages:

![image](https://cloud.githubusercontent.com/assets/3164826/5310910/d05232f0-7bf8-11e4-8482-adab07c07997.png)

And it doesn't trigger any display malfunction in XCode:

![image](https://cloud.githubusercontent.com/assets/3164826/5310926/04a3ddc4-7bf9-11e4-85c0-65c6d997eb5c.png)

That's all.

[EOF]
