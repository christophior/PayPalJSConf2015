# Scalable CSS -> Concrete CSS

Examples: http://github.paypal.com/hdoan/Examples

Talk about concrete CSS solutions for design/product requirements.

Solutions meet the following:
1. HTML is semantics

2. Consice

3. Works when content grows/shrinks

4. Works on all browsers


## No wrapping solutions
```
.buzzword {
	white-space: nowrap
}
```

Non-conrete solutions
1. remove words
2. Add <br/>

Concrete solution:
1. white-space: nowrap;
2. display: inline-block;


### input with fix-width controls
can use flexbox
can use measurements in percentages

#### Flexbox
```
.container {
	display: flex;
}

.textInput {
	flex: 1;
}

.btn1 {
	width: 56px;
}

.btn2 {
	width: 40px
}
```

#### not using flexbox
// incomplete
```
.container {
	display: table;
	width: 100%;
}

.textInput {
}

.btn1 {
	width: 56px;
}

.btn2 {
	width: 40px
}
```

### iframe problem on mobile devices
fix (go on mobile): http://hoaboat.github.io

click on 'over panel with scrolling' link