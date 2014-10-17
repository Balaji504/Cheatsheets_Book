# Regular Expressions

### Creditcard
A valid credit card number

```
^((4\d{3})|(5[1-5]\d{2})|(6011)|(7\d{3}))-?\d{4}-?\d{4}-?\d{4}|3[4,7]\d{13}$]
```

### Date (US)
Date in US format with support for leap years.

```
^(?:(?:(?:0?[13578]|1[02])(\/|-|\.)31)\1|(?:(?:0?[1,3-9]|1[0-2])(\/|-|\.)(?:29|30)\2))(?:(?:1[6-9]|[2-9]\d)?\d{2})$|^(?:0?2(\/|-|\.)29\3(?:(?:(?:1[6-9]|[2-9]\d)?(?:0[48]|[2468][048]|[13579][26])|(?:(?:16|[2468][048]|[3579][26])00))))$|^(?:(?:0?[1-9])|(?:1[0-2]))(\/|-|\.)(?:0?[1-9]|1\d|2[0-8])\4(?:(?:1[6-9]|[2-9]\d)?\d{2})$]
```

### E-mail
A valid -email address

```
^[a-zA-Z0-9+&*-]+(?:\.[a-zA-Z0-9_+&*-]+)*@(?:[a-zA-Z0-9-]+\.)+[a-zA-Z]{2,7}$]
```

### English daywords
English 2 character abbreviations for the days of the week.

```
^(Mo|Tu|We|Th|Fr|Sa|Su)$]
```

### English digitwords
The English words representing the digits 0 to 9.

```
^(zero|one|two|three|four|five|six|seven|eight|nine)$]
```

### English monthwords
English 3 character abbreviations for the months.

```
^(Jan|Feb|Mar|Apr|May|Jun|Jul|Aug|Sep|Oct|Nov|Dec)$]
```

### French digitwords
The French words representing the digits 0 to 9.

```
^(z[eé]ro|un|deux|trois|quatre|cinq|six|sept|huit|neuf)$]
```

### German digitwords
The German words representing the digits 0 to 9.

```
^(null|eins|zwei|drei|vier|f(ue|ü)nf|sechs|sieben|acht|neun)$]
```

### IP
A valid IP Address

```
^(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$]
```

### Password
4 to 8 character password requiring numbers and both lowercase and uppercase letters

```
^(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{4,8}$]
```

### Password (Complex)
4 to 32 character password requiring at least 3 out 4 (uppercase and lowercase letters, numbers and special characters) and no more than 2 equal characters in a row

```
^(?:(?=.*\d)(?=.*[A-Z])(?=.*[a-z])|(?=.*\d)(?=.*[^A-Za-z0-9])(?=.*[a-z])|(?=.*[^A-Za-z0-9])(?=.*[A-Z])(?=.*[a-z])|(?=.*\d)(?=.*[A-Z])(?=.*[^A-Za-z0-9]))(?!.*(.)\1{2,})[A-Za-z0-9!~<>,;:_=?*+#."&§%°()\|\[\]\-\$\^\@\/]{8,32}$]
```

### Phone number (US)
US phone number with or without dashes.

```
^\D?(\d{3})\D?\D?(\d{3})\D?(\d{4})$]
```

### Safetext
Lower and upper case letters and all digits.

```
^[a-zA-Z0-9 .-]+$]
```

### Social security number (SSN) (US)
9 digit U.S. social security number with dashes.

```
^\d{3}-\d{2}-\d{4}$]
```

### Spanish digitwords
The Spanish words representing the digits 0 to 9

```
^(cero|uno|dos|tres|cuatro|cinco|seis|siete|ocho|nueve)$]
```

### States (US)
2 letter U.S. state abbreviations.

```
^(AE|AL|AK|AP|AS|AZ|AR|CA|CO|CT|DE|DC|FM|FL|GA|GU|HI|ID|IL|IN|IA|KS|KY|LA|ME|MH|MD|MA|MI|MN|MS|MO|MP|MT|NE|NV|NH|NJ|NM|NY|NC|ND|OH|OK|OR|PW|PA|PR|RI|SC|SD|TN|TX|UT|VT|VI|VA|WA|WV|WI|WY)$]
```

### URL
A valid URL per the URL spec.

```
^((((https?|ftps?|gopher|telnet|nntp)://)|(mailto:|news:))(%[0-9A-Fa-f]{2}|[-()_.!~*';/?:@&=+$,A-Za-z0-9])+)([).!';/?:,][[:blank:]])?$]
```

### Zip code (US)
US zip code with optional dash-four.

```
^\d{5}(-\d{4})?$]
```

## Verify
### HTML HEX CODE
^#?([a-f]|[A-F]|[0-9]){3}(([a-f]|[A-F]|[0-9]){3})?$

### FLOATING POINT
^[-+]?[0-9]+[.]?[0-9]*([eE][-+]?[0-9]+)?$

### PERSON NAME
^[a-zA-Z]+(([',. -][a-zA-Z ])?[a-zA-Z]*)*$

### MAC ADDRESS
^([0-9a-fA-F][0-9a-fA-F]:){5}([0-9a-fA-F][0-9a-fA-F])$

### GUID
^[A-Z0-9]{8}-[A-Z0-9]{4}-[A-Z0-9]{4}-[A-Z0-9]{4}-[A-Z0-9]{12}$

### IP ADDRESS v4
^\b((25[0-5]|2[0-4]\d|[01]\d\d|\d?\d)\.){3}(25[0-5]|2[0-4]\d|[01]\d\d|\d?\d)\b$

### IP ADDRESS v6
(^\b(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\b$

### REASONABLE DOMAIN NAME
^([a-zA-Z0-9]([a-zA-Z0-9\-]{0,61}[a-zA-Z0-9])?\.)+[a-zA-Z]{2,6}$

### RFC 1918 NON ROUTABLE IP
^(((25[0-5]|2[0-4][0-9]|19[0-1]|19[3-9]|18[0-9]|17[0-1]|17[3-9]|1[0-6][0-9]|1[1-9]|[2-9][0-9]|[0-9])\.(25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9][0-9]|[0-9]))|(192\.(25[0-5]|2[0-4][0-9]|16[0-7]|169|1[0-5][0-9]|1[7-9][0-9]|[1-9][0-9]|[0-9]))|(172\.(25[0-5]|2[0-4][0-9]|1[0-9][0-9]|1[0-5]|3[2-9]|[4-9][0-9]|[0-9])))\.(25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9][0-9]|[0-9])\.(25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9][0-9]|[0-9])$

### VALID WINDOWS FILENAME
^(?!^(PRN|AUX|CLOCK\$|NUL|CON|COM\d|LPT\d|\..*)(\..+)?$)[^\x00-\x1f\\?*:\";|/]+$

### Java Classname
^(([a-z])+.)+[A-Z]([a-z])+$

### ANY PLATFORM FILENAME
^(([a-zA-Z]:|\\)\\)?(((\.)|(\.\.)|([^\\/:*?"|<>. ](([^\\/:*?"|<>. ])|([^\\/:*?"|<>]*[^\\/:*?"|<>. ]))?))\\)*[^\\/:*?"|<>. ](([^\\/:*?"|<>. ])|([^\\/:*?"|<>]*[^\\/:*?"|<>. ]))?$
