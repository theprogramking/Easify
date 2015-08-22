EasifyJS
===============

A small library that makes JavaScript easier to work with.

---------------

##DOCUMENTATION

To get started, include Easify.min.js in your website. Make sure it's included above your websites JS file. To make sure JS doesn't interfere with the loading of your HTML and CSS, it is suggested that you add your JS files right above your closing `body` tag.

```html
    <script src="js/Easify.min.js"></script>
    <script src="js/app.js"></script>
  </body>
</html>
```

You'll know it's included if you look in the console and see 'Easify loaded!'

Once included, you'll need to initialize an Easify object. There are 2 ways to do this:

```javascript
// The long hand version
var e = Easify();

// The preferred method
var e = $E();

// Will be using the 'e' variable for the rest of this section
````

Now you can access all of the Easify methods by using dot notation.

####String Methods

***capitalize***

Used to capitalize the first letter of a provided string.

```javascript
e.capitalize('john'); // > "John"
```

***isString***

Used to check if the provided value is of type 'string'.

```javascript
e.isString('hello world'); // > true
e.isString(33); // > false
```

***last***

Used to get the last letter of a string.

```javascript
e.last('hello world'); // > "d"
```

***remove***

Used to remove a specified amount of random letters from a provided string.

```javascript
e.remove('hello world', 4); // > "hell od"
e.remove('hello world', 4); // > "heloorl"
```

***removeAll***

Used to remove all instances of a specified letter from a provided string.

```javascript
e.removeAll('hello world', 'l'); // > "heo word"
```

***randomize***

Used to randomly sort the letters in a provided string.

```javascript
e.randomize('hello world'); // > "lrdlwloeho "
e.randomize('hello world'); // > "roheodlw ll"
```

***repeat***

Used to repeate a provided string, a specified amount of times. Also trims off white space from the beginning and end.

```javascript
e.repeat('John ', 3); // > "John John John";
```

***reverse***

Used to reverse the order of a string.

```javascript
e.reverse('hello world'); // > "dlrow olleh"
```

***wrap***

Used to wrap a provided string inside of a provided HTML element.

```javascript
e.wrap('hello world', 'h1'); // > "<h1>hello world</h1>"
```

####ARRAY METHODS

***checkTypes***

Used to check the types of all values contained in a passed in array

```javascript
e.checkTypes([{}, [], 'hello', 3, function(){}, true]); // > ["object", "array", "string", "number", "function", "boolean"]
```

***contains***

Used to check if a specific value is inside of an array

```javascript
e.contains([1,2,3], 4); // > false
e.contains([1,2,3], 2); // > true
```

***isArray***

Used to check if passed in value is an array

```javascript
e.isArray([]); // > true
e.isArray({}); // > false
e.isArray('hello'); // > false
```

####OBJECT METHODS

***isObject***

Used to check if passed in value is an object

```javascript
e.isObject({}); // > true
e.isObject([]); // > false
e.isObject(4); // > false
```

####DOM Methods

***insertHTML***

Used to insert text or HTML into a selected element. Can be used with id or class selectors. If class is selected, a 4th(optional) parameter can be used to specify how many will be affected, starting from the first.

```javascript
// This will place 'hello world' inside of the element with an id of #id-name
e.insertHTML('id', 'id-name', 'hello world');

// This will place 'hello world' inside of all elements with the class of .class-name
e.insertHTML('class', 'class-name', 'hello world');

// This will place 'hello world' inside of 2 elements with the class of .class-name
e.insertHTML('class', 'class-name', 'hello world', 2);

// Note: If the amount argument is more than the amount of elements with
// the specified classname, the amount argument will default to actual
// amount of elements.
```

***elementFromId***

Returns the DOM element with the given ID.

```javascript
// Will return the element with the #heading ID. If it doesn't exist, it will return null.
e.elementFromId('heading');
```

####Universal Methods

***isEqual***

Returns true if both arguments are equal (strict).

```javascript
e.isEqual(5, 5); // > true
e.isEqual(5, '5'); // > false
e.isEqual('hello', 'hello'); // > true
```

***isNotEqual***

Returns true if both arguments are not equal (strict).

```javascript
e.isNotEqual(5, 5); // > false
e.isNotEqual(5, '5'); // > true
e.isNotEqual('hello', 'Hello'); // true
```

***isSimilar***

Returns true if both arguments are equal (not strict).

```javascript
e.isSimilar(5, 5); // > true
e.isSimilar(5, '5'); // > true
e.isSimilar('hello', 'Hello'); // > false
```

***isNotSimilar***

Returns true if both arguments are not equal (not strict).

```javascript
e.isNotSimilar(5, 5); // > false
e.isNotSimilar(5, '5') // > false
e.isNotSimilar('hello', 'Hello'); // > true
```

***isTruthy***

Returns true if input is truthy value.

```javascript
// Numbers
e.isTruthy(0); // > false
e.isTruthy(1); // > true

// Strings
e.isTruthy(''); // > false
e.isTruthy('hello'); // > true

// Arrays
e.isTruthy([]); // > true
e.isTruthy([1, 2, 3]); // > true

// Objects
e.isTruthy({}); // > true
e.isTruthy({a: 1, b: 2, c: 3}); // > true

// Functions
e.isTruthy(function(){}); // > true
```

***isFalsey***

Returns true if input is falsey value.

```javascript
// Numbers
e.isFalsey(0); // > true
e.isFalsey(1); // > false

// Strings
e.isFalsey(''); // > true
e.isFalsey('hello'); // > false

// Arrays
e.isFalsey([]); // > false
e.isFalsey([1, 2, 3]); // > false

// Objects
e.isFalsey({}); // > false
e.isFalsey({a: 1, b: 2, c: 3}); // > false

// Functions
e.isFalsey(function(){}); // > false
```

***checkType***

Returns the type of a passed in value

```javascript
e.checkType([]); // > "array"
e.checkType({}); // > "object"
e.checkType('hello'); // > "string"
e.checkType(3); // > "number"
e.checkType(true); // > "boolean"
```


##CONTRIBUTE

Currently, there are 2 ways you can contribute to this project:

1. Submit an issue. When submitting an Issue please precede the title with some sort of category so it can easily be identified. Please make sure the category is all caps and is followed by a colon. (ex. WEBSITE:, BUG FIX:, FEATURE REQUEST:, etc.)

2. You can submit code via Pull Request. Before submitting a pull request, make sure you submit an issue to see if your idea is already being worked on by someone else. The list of issues is also a great place to start looking if you want to get into this project. If you want to start working on one of the issues, just submit a reply letting everyone know that you're planning on tackling it. This will keep a bunch of people from working on the same issues.

In the future, this section will be moved into a CONTRIBUTE.md file along with anything else deemed necessary. For now it's small enough to just leave here.


##TESTS

To run tests is simple, just open test/index.html in your browser of choice and click the "Run Tests" button. You'll see a long list of the tests that were run and whether they passed or failed.

To make sure all the tests were run, look in the console for a line that says, "Tests run!"

Tests are very simple to implement. Here's the format:

```javascript
// This is where you put your description of the test and any
// amplifying information.
tests.push(
  function() {
    var text = "Short description that will appear when testing";
    runTest(comparison, text);
  }
);
```

Here is an example of a real world test:

```javascript
// Checks if capitalize() returns a string with the first letter capitalized
  tests.push(
    function() {
      var text = "capitalize() returns a new string with the first letter capitalized";
      runTest(e.capitalize('testing') === 'Testing', text);
    }
  );
```

##FINAL NOTES

The website portion of this uses AngularJS so if things look a little odd in your forked version, it's because you need to run it in some sort of server. If you're using [Brackets](http://brackets.io/) as your text editor, you should be good if you hit the preview button from website/index.html.