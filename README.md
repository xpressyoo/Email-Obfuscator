# Email Obfuscator

Easy-to-use substitution cipher encrypting via ROT13 email addresses to avoid them getting harvested by spam-bots while keeping the mailto: feature. It rests on JavaScript and includes a pure CSS fallback.

## ROT13 function (JavaScript)

    String.prototype.rotate  = function() { 
                return this.replace(/[a-z0-9]/ig, function(chr) {
                var cc = chr.charCodeAt(0);
                if (cc >= 65 && cc <= 90) cc = 65 + ((cc - 52) % 26);
                else if (cc >= 97 && cc <= 122) cc = 97 + ((cc - 84) % 26);
                else if (cc >= 48 && cc <= 57) cc = 48 + ((cc - 43) % 10);
                return String.fromCharCode(cc);
                    			});
			};

## Reverse strings (CSS fallback)

    String.prototype.reverse = function() {

        return this.split( '' ).reverse().join( '' ); 
          
          };
