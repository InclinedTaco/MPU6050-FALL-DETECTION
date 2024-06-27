Editor.md
Open source online Markdown editor.

##BEFORE YOU PROCEED
​
- #####MPU6050 is old,noisy and the documentation SUCKS,go for other IMUs.If you have a MPU6050 lying and just wanna tinker with it,then fine.
- #####This is a very simple implementation of fall detection and you would need to use Kalman filters and stuff to make it more accurate. It does not make sense to do that much on an MPU6050. Again, just go for another IMU if possible.
​
​
​
##UNDERSTANDING THE REGISTERS
- The two registers, FF_THR (0x1D) AND FF_DUR (0X1E) which can be used to set the acceleration threshold and duration to trigger an interrupt.
-  For the FF_THR, 1LSB=2mg and it increments the FF_DUR (1LSB=1ms) by 1 if the acceleration value in each one of the axis is less than the threshold value and it decrements the FF_DUR if it is above the threshold value. When the time crosses the FF_DUR value, it triggers an interrupt.
- To enable the free fall interrupt we must set the 7th bit of INT_ENABLE (0x38) to 1 and the status of free fall interrupt can be read from the 7th bit of INT_STATUS (0x3A).
- Perform bitwise manipulation of the rgisters rather than wrting an 8 bit data directly (you can do it but only if you are sure about all the other 7 bits.)
​
####[Here is the register map](https://www.i2cdevlib.com/devices/mpu6050#registers) 
​
​
BEFORE YOU PROCEED
MPU6050 is old,noisy and the documentation SUCKS,go for other IMUs.If you have a MPU6050 lying and just wanna tinker with it,then fine.
This is a very simple implementation of fall detection and you would need to use Kalman filters and stuff to make it more accurate. It does not make sense to do that much on an MPU6050. Again, just go for another IMU if possible.
UNDERSTANDING THE REGISTERS
The two registers, FF_THR (0x1D) AND FF_DUR (0X1E) which can be used to set the acceleration threshold and duration to trigger an interrupt.
For the FF_THR, 1LSB=2mg and it increments the FF_DUR (1LSB=1ms) by 1 if the acceleration value in each one of the axis is less than the threshold value and it decrements the FF_DUR if it is above the threshold value. When the time crosses the FF_DUR value, it triggers an interrupt.
To enable the free fall interrupt we must set the 7th bit of INT_ENABLE (0x38) to 1 and the status of free fall interrupt can be read from the 7th bit of INT_STATUS (0x3A).
Perform bitwise manipulation of the rgisters rather than wrting an 8 bit data directly (you can do it but only if you are sure about all the other 7 bits.)
Here is the register map
Example
<link rel="stylesheet" href="editormd/css/editormd.css" />
<div id="test-editor">
    <textarea style="display:none;">### Editor.md

**Editor.md**: The open source embeddable online markdown editor, based on CodeMirror & jQuery & Marked.
    </textarea>
</div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
<script src="editormd/editormd.min.js"></script>
<script type="text/javascript">
    $(function() {
        var editor = editormd("test-editor", {
            // width  : "100%",
            // height : "100%",
            path   : "editormd/lib/"
        });
    });
</script>Copy
More Examples >>

Features
Support Standard Markdown / CommonMark and GFM(GitHub Flavored Markdown);
Full-featured: Real-time Preview, Image (cross-domain) upload, Preformatted text/Code blocks/Tables insert, Code fold, Search replace, Read only, Themes, Multi-languages, L18n, HTML entities, Code syntax highlighting...;
Markdown Extras : Support ToC (Table of Contents), Emoji, Task lists, @Links...;
Support TeX (LaTeX expressions, Based on KaTeX), Flowchart and Sequence Diagram of Markdown extended syntax;
Support identification, interpretation, fliter of the HTML tags;
Support AMD/CMD (Require.js & Sea.js) Module Loader, and Custom/define editor plugins;
Compatible with all major browsers (IE8+), compatible Zepto.js and iPad;
Support Custom theme styles;
Download & install
Latest version: v1.5.0，Update: 2015-06-09



 


Or NPM install:

npm install editor.md



Or Bower install:

bower install editor.md




Change logs:

CHANGES

Dependents
Projects :

CodeMirror
marked
jQuery
FontAwesome
github-markdown.css
KaTeX
Rephael.js
prettify.js
flowchart.js
sequence-diagram.js
Prefixes.scss

Development tools :

Visual Studio Code
Sass/Scss
Gulp.js
License
Editor.md follows the MIT License, Anyone can freely use.





Fork me on Github :







Users

 Contact Us: editor.md@ipandao.com


Editor.md
Copyright © 2015-2019 Editor.md, MIT license.

Design & Develop By: Pandao     
