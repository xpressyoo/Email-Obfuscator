# Email Obfuscator

Easy-to-use [substitution cipher](http://en.wikipedia.org/wiki/Substitution_cipher) encrypting via [ROT13](http://en.wikipedia.org/wiki/ROT13) email addresses to avoid them getting harvested by spam-bots while keeping the mailto: feature. It rests on JavaScript and includes a pure CSS fallback. See file "obfuscator.html" for more details.

### ROT13 function (JavaScript)

    String.prototype.rotate  = function() { 
                return this.replace(/[a-zA-Z]/ig, function(chr) {
                var cc = chr.charCodeAt(0);
                if (cc >= 65 && cc <= 90) cc = 65 + ((cc - 52) % 26);
                else if (cc >= 97 && cc <= 122) cc = 97 + ((cc - 84) % 26);
                else if (cc >= 48 && cc <= 57) cc = 48 + ((cc - 43) % 10);
                return String.fromCharCode(cc);
                    			});
			};

### Reverse strings (CSS fallback)

    String.prototype.reverse = function() {

        return this.split( '' ).reverse().join( '' ); 
          
          };
          
### Display & De-cipher the mailto

    
    <span id="obf">
    <script>
    document.getElementById("obf").innerHTML="<n uers=\\"znvygb:' + email + subject +'\\">' + anchor + '</n>\".replace(/[a-z0-9]/g,function(c){return String.fromCharCode((c<="Z"?90:122)>=(c=c.charCodeAt(0)+13)?c:c-26);});
    </script>
          
where variables "email", "subject" and "anchor" have been retrieved from input fields and rotated thanks to the rotate() function.

-----------------------------------------------------------

Copyright (c) 2012 [Florian Bersier](http://www.florianbersier.com) | MIT Licensed 

