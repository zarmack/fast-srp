# fast-srp

Is a pure [NodeJS](https://nodejs.org/) implementation of the [SRP6a protocol](http://srp.stanford.edu/).

It's a derived work of [Jed Parson](http://jedparsons.com/)'s [node-srp](https://github.com/jedp/node-srp) and [Tom Wu](http://www-cs-students.stanford.edu/~tjw/)'s [jsbn](http://www-cs-students.stanford.edu/~tjw/jsbn/).

node-srp uses [bignum](https://github.com/justmoon/node-bignum) to handle the big numbers, but I've got many problems with that library mainly compiling it in Windows 7. Finally I've ported the node-srp to use [jsbn](http://www-cs-students.stanford.edu/~tjw/jsbn/).
