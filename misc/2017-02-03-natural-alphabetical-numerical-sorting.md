# Alphabetical Numerical Sorting or Natural Sorting

## StackOverflow Questions

### Idea 1: Create a costomized comparator function

- [Javascript : natural sort of alphanumerical strings](http://stackoverflow.com/questions/2802341/javascript-natural-sort-of-alphanumerical-strings)
- [Sort mixed alpha/numeric array](http://stackoverflow.com/questions/4340227/sort-mixed-alpha-numeric-array?answertab=votes#tab-top)


```javascript
// Comparator function @epascarello
// Source: http://stackoverflow.com/questions/4340227/sort-mixed-alpha-numeric-array
var reA = /[^a-zA-Z]/g;
var reN = /[^0-9]/g;
function sortAlphaNum(a,b) {
    var aA = a.replace(reA, "");
    var bA = b.replace(reA, "");
    if(aA === bA) {
        var aN = parseInt(a.replace(reN, ""), 10);
        var bN = parseInt(b.replace(reN, ""), 10);
        return aN === bN ? 0 : aN > bN ? 1 : -1;
    } else {
        return aA > bA ? 1 : -1;
    }
}
```

```javascript
// Source: http://www.davekoelle.com/files/alphanum.js


/* ********************************************************************
 * Alphanum sort() function version - case sensitive
 *  - Slower, but easier to modify for arrays of objects which contain
 *    string properties
 *
 */
function alphanum(a, b) {
  function chunkify(t) {
    var tz = new Array();
    var x = 0, y = -1, n = 0, i, j;

    while (i = (j = t.charAt(x++)).charCodeAt(0)) {
      var m = (i == 46 || (i >=48 && i <= 57));
      if (m !== n) {
        tz[++y] = "";
        n = m;
      }
      tz[y] += j;
    }
    return tz;
  }

  var aa = chunkify(a);
  var bb = chunkify(b);

  for (x = 0; aa[x] && bb[x]; x++) {
    if (aa[x] !== bb[x]) {
      var c = Number(aa[x]), d = Number(bb[x]);
      if (c == aa[x] && d == bb[x]) {
        return c - d;
      } else return (aa[x] > bb[x]) ? 1 : -1;
    }
  }
  return aa.length - bb.length;
}


/* ********************************************************************
 * Alphanum sort() function version - case insensitive
 *  - Slower, but easier to modify for arrays of objects which contain
 *    string properties
 *
 */
function alphanumCase(a, b) {
  function chunkify(t) {
    var tz = new Array();
    var x = 0, y = -1, n = 0, i, j;

    while (i = (j = t.charAt(x++)).charCodeAt(0)) {
      var m = (i == 46 || (i >=48 && i <= 57));
      if (m !== n) {
        tz[++y] = "";
        n = m;
      }
      tz[y] += j;
    }
    return tz;
  }

  var aa = chunkify(a.toLowerCase());
  var bb = chunkify(b.toLowerCase());

  for (x = 0; aa[x] && bb[x]; x++) {
    if (aa[x] !== bb[x]) {
      var c = Number(aa[x]), d = Number(bb[x]);
      if (c == aa[x] && d == bb[x]) {
        return c - d;
      } else return (aa[x] > bb[x]) ? 1 : -1;
    }
  }
  return aa.length - bb.length;
}

```

### Idea 2: For each item, return a customized value

- [Sort numbers with letters numerically and alphabetically](http://stackoverflow.com/questions/17996193/sort-numbers-with-letters-numerically-and-alphabetically)



## Tech Blog

- [David koelle's article on the subject](http://www.davekoelle.com/alphanum.html)
- [Brian Huisman's javascript solutions](http://www.davekoelle.com/files/alphanum.js)
