# fast-srp

Is a pure [NodeJS](https://nodejs.org/) implementation of the [SRP6a protocol](http://srp.stanford.edu/).

It's a derived work of [Jed Parson](http://jedparsons.com/)'s [node-srp](https://github.com/jedp/node-srp) and [Tom Wu](http://www-cs-students.stanford.edu/~tjw/)'s [jsbn](http://www-cs-students.stanford.edu/~tjw/jsbn/).

node-srp uses [bignum](https://github.com/justmoon/node-bignum) to handle the big numbers, but I've got many problems with that library mainly compiling it in Windows 7. Finally I've ported the node-srp to use [jsbn](http://www-cs-students.stanford.edu/~tjw/jsbn/).


## Creating the Verifier
```javascript
'use strict';

var srp6a = require('fast-srp');

//
// I:
var srp6a_create_user = function(I, P, callback) {
  srp6a.genKey(32, function(error, salt) {
	  if(error) {
	    callback(error);
	  }
	  var v = srp6a.computeVerifier(srp6a.params[4096], salt, new Buffer(I), new Buffer(P));
	  callback(null, v);
  });
}

srp6a_create_user('Zarmack Tanen', '*****', function(error, verifier) {
  if(error)
    throw error;
  console.log("SRP6a verifier of Zarmack Tanen user is " + verifier.toString('hex'));
});
```
