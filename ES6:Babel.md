# ES6 & Babel

## To try out Babel head to: http://babeljs.io/repl/

### Default paramters
```
function(var = 50) { ... } // var is set to 50 by default
```

### Template literals
```
var name = first + ' ' + last;
// magically becomes
var name = `$(first) $(last)`;
// need to use ` to get advanced functionality
```

#### another use for template literals
```
var x = '
some long block of content
that goes in many lines
';
```

### Destructuring
```
// jquery example
var data = $('body').data(),
	house = data.house,
	mouse = data.mouse;

// destructuring allows you to do the following
var {house, mouse} = $('body').data();
```

Grabbing out middleware from a module and saving it to a var with the same name
```
var {middleware} = require('...');
```

#### Destructuring arrays
```
var [column1, column2] = $('.column');
```

Examples:
```
let a = [1, 2, 3]
let [,,third] = a;
// same as third = a.third;

let person = {
	name: {
		first: "Chris",
		last: "Villarreal"
	},
	age: "unknown"
}

var {name} = person;
// same as name = person.name;
```

### Arrow functions
```
// Example 1
var people = [
	{name: "suzie", age: 26},
	{name: "joe", age: 32},
	{name: "sally", age: 5}
];

var greetings = people
	.filter(person => person.age > 18)
	.map(person => "Hello " + person.name);

// Example 2
var self = this;
$.get("/awesome/api", data => {
	this.doSomethingWith(data);
});

//////

var sayHi = () => console.log("hi");
var getName = (person) => person.name;
var longThing
```

### All of the Above
```
function getUser(id) {
	var id = id || USER_ID;
	$.get('/people/' + id, function(person) {
		var age = person.age;
		var name = person.name;
		console.log('Name is ' + name);
		console.log('Age is ' + age);
	});
}

// after converting to ES6 using all of the above

let getUser = (id = USER_ID) => {
	$.get('/people/' + id, (person) => {
		var {age, name} = person;
		console.log(`Name is $(name)`);
		console.log(`Age is $(age)`);
	});	
};
```

### REST/Spread
```
let array  = [1, 2, 3];
let x = [];

x.push(array);
// results in x == [[1, 2, 3]];

x.push(...array);
// results in x == [1, 2, 3] 
```

```
let person = {
	name: "sam",
	age: 24
};

let me = {...person, name: "chris"};
console.log(me);
// {name: "chris", age: 24}
```