# node-entropy

Shannon Entropy calculation to measure the information gain of an array of objects (i.e. average unpredictability in a random variable) in bits.

The algorithm is based on the formula

![equation](http://www.sciweavers.org/tex2img.php?eq=H%28X%29%20%3D%20-%5Csum_%7Bx%20%5Cin%20%5Cmathcal%7BX%7D%7D%20p%28x%29%20%5Clog_2%20p%28x%29&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)

## Installation

```
$ npm install entropy
```

## Usage

```
var entropy = require('entropy');

entropy.calculateEntropy(items, columns, function(entropy) {
	console.log(entropy);
});
```

```items``` is an array of objects on which the entropy algorythm is performed. The ```columns``` array includes all the keys of the object the entropy should be calculated of. 

### Example

```javascript
var entropy = require('entropy');

var items = [
    {
      name: "Alex",
      email: "hello@example.com",
      year: 1980
    }, {
      name: "Peter",
      email: "peter@example.com",
      year: 1990
    }, {
      name: "Bob",
      email: "bob@example.com",
      year: 2000
    }
  ];

var columns = ["name", "email", "year"];

entropy.calculateEntropy(items, columns, function(entropy) {
	console.log(entropy);
});
```

#### Output

The entropy of each property in bits.

```javascript
{ 
	name: 4.754887502163468, 
	email: 2.7548875021634687, 
	year: 0 
}
```


## Tests

```
$ npm test
```

## Contributing

* Create something awesome, make the code better, add some functionality,
  whatever (this is the hardest part).
* [Fork it](http://help.github.com/forking/)
* Create new branch to make your changes
* Commit all your changes to your branch
* Submit a [pull request](http://help.github.com/pull-requests/)

## Contact

Feel free to get in touch.

* Website: <http://schuch.me> 
* Twitter: [@schuchalexander](http://twitter.com/schuchalexander)

## Licence

Copyright (C) 2013 Alexander Schuch

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.