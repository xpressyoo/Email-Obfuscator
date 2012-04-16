# Email Obfuscator

Easy-to-use [substitution cipher](http://en.wikipedia.org/wiki/Substitution_cipher) encrypting via [ROT13](http://en.wikipedia.org/wiki/ROT13) email addresses to avoid them getting harvested by spam-bots while keeping the mailto: feature. It rests on JavaScript and includes a pure CSS fallback. See file "obfuscator.html" for more details.

### ROT13 function (JavaScript)

    String.prototype.rotate  = function() { 
                return this.replace(/[a-z0-9]/ig, function(chr) {
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
          
          
# MIT License

Copyright (c) 2012 [Florian Bersier](http://www.florianbersier.com)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation 
files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, 
copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom 
the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES 
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY 
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH 
THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
