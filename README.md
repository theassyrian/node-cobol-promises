<!---------------------------------------------------------------------------->
<!-- STOP, LOOK & LISTEN!                                                   -->
<!-- ====================                                                   -->
<!-- Do NOT edit this file directly since it's generated from a template    -->
<!-- file, using https://github.com/IonicaBizau/node-blah                   -->
<!--                                                                        -->
<!-- If you found a typo in documentation, fix it in the source files       -->
<!-- (`lib/*.js`) and make a pull request.                                  -->
<!--                                                                        -->
<!-- If you have any other ideas, open an issue.                            -->
<!--                                                                        -->
<!-- Please consider reading the contribution steps (CONTRIBUTING.md).      -->
<!-- * * * Thanks! * * *                                                    -->
<!---------------------------------------------------------------------------->

![cobol-promises](http://i.imgur.com/DfsVV3F.png)

# cobol-promises [![Donate now][donate-now]][paypal-donations]

COBOL bridge for NodeJS with promises support.

## Installation

```sh
$ npm i cobol-promises
```

## Example

```js
// Dependencies
var Cobol = require("cobol-promises")
  , Promise = require("promiscuous")
  ;

// Create a hello world
var helloWorld1 = Cobol(function () { /*
       IDENTIFICATION DIVISION.
       PROGRAM-ID. HELLO.
       PROCEDURE DIVISION.

       PROGRAM-BEGIN.
       DISPLAY "Hello world".

       PROGRAM-DONE.
       STOP RUN.
 */ });

// Create another hello world
var helloWorld2 = Cobol(function () { /*
       IDENTIFICATION DIVISION.
       PROGRAM-ID. HELLO.
       PROCEDURE DIVISION.

       PROGRAM-BEGIN.
       DISPLAY "Hello world second time!".

       PROGRAM-DONE.
       STOP RUN.
 */ });

Promise.all([helloWorld1, helloWorld2]).then(function (res) {
    console.log(res);
}).catch(function(err) {
    console.log("Something bad happened!" + err);
});
// => ["Hello world", "Hello world second time!"]

```

## Documentation

### `CobolPromises(input, options, callback)`
The function receives the [same parameters like the `cobol` package](https://github.com/IonicaBizau/node-cobol#documentation), but returns a promise.

#### Params
- **Object** `input`: See [`cobol` docs](https://github.com/IonicaBizau/node-cobol#documentation).
- **Object** `options`: See [`cobol` docs](https://github.com/IonicaBizau/node-cobol#documentation).
- **Function** `callback`: See [`cobol` docs](https://github.com/IonicaBizau/node-cobol#documentation).

#### Return
- **Promise** The COBOL promise you.

## How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].

## License
[KINDLY][license] © [Ionică Bizău][website]–The [LICENSE](/LICENSE) file contains
a copy of the license.

[license]: http://ionicabizau.github.io/kindly-license/?author=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica@gmail.com%3E&year=2015
[contributing]: /CONTRIBUTING.md
[website]: http://ionicabizau.net
[docs]: /DOCUMENTATION.md
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=MG98D7NPFZ3MG
[donate-now]: http://i.imgur.com/jioicaN.png