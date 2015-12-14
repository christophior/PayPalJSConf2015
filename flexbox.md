# Using Flex Box Workshop

## use flex property to center a box
```
 .class {
 	display: flex
	justify-content: center
 }
 ```


## Responsive input fields

### usual attempt:
define box, define a class for each row, put inputs in each row

### solution:
html:
```
	.box
		.items
			.item
			.item
		.items
			.item
			.item
```

css:
```
	.items {
		display: flex;
		flex-wrap: wrap;
	}
	.item {
		flex: 1 0 200px;
	}
	// responsive; just add the following
	// didn't have time to type it out :/
```

Flexbox supports all browsers