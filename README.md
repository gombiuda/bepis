<p align=center>
  <img src="readme-images/bepis-logo.jpg?raw=true" alt="Bepis Logo">
</p>

# bepis

Bepis is a crazy new way to write HTML + CSS in JavaScript.

## Examples

Just some simple examples you can play with it online [here](https://jsfiddle.net/rjze2n3p/2/).

```javascript

// setup constants
const o = null;
const {body} = document;
const myStyle = {
color: '#808080',
background: 'linear-gradient(to right, lime, dodgerblue)',
margin: 0
};

// form with 1 field
w`form ${o} ${myStyle} p label ${"Name"} input ${{type:'text', placeholder:'your name'}}`(body);

// form with 2 field
w`form ${o} ${myStyle}, 
	p label ${"Name"} input ${{required: true, type:'text', placeholder:'your name'}}.
	p label ${"Email"} input ${{required: true, type:'email', placeholder:'your email'}}.
	p label ${"Password"} input ${{required: true, type:'password', placeholder:'your password'}}.
	p button ${"Sign up"} 
`(body);

// form with 3 field
w`ul, 
	li ${"Option 1"}, 
	li ${"Option 2"},
		p input ${{type:'submit'}}.
		p form button ${"SAVE"}.
	.
	li ${"Option 3"}.
`(body);
```

## Get

```
$ npm i bepis
```

## Tutorial

**Format**

```
w`tag-list ${content} ${style}`(insertionPoint)
```
where
- tag-list := [html-tag-name ]+
- content := string | object | null
- style := object | null

**Also**:
- Use template literals tagged with `w`
- Use ',' operator to save an insertion point
- Use '.' operator to load an insertion point
- After a tag path the first parameter is the content (string or Element properties object)
- After a tag path the second parameter is the style (inline style object scoped to that element)
- A tagged template literal returns an insertion function. Call that function with the Element you want to append this markup to.
- Whitespace in the template literal has no special meaning and, except to separate tags, is ignored.
- If you want to use the style parameter, but not the content parameter you need to put a null or undefined in the content parameter. I do this in the examples by using a variable set to null.

## Why Bepis?

Bepis is meant to be a quick and easy and small way to write HTML from JS. Personally I didn't used to mind writing angle brackets and equals signs and closing tags, but eventually I just got sick of it. Not to the extent that I hate doing it, just to the extent that when I don't have to worry about writing dynamic updating HTML, I want something easy. Bepis was built to be a friend to building business landing pages fast. I figure I can write HTML in bepis faster than writing HTML.

## DesiGn pHilOsOPHy

Bepis is designed to be concise and crazy. It should work but it's not suitable for any production environment. It's highly experimental.

Also bepis is not meant for dynamic *updating* of HTML, only dynamic creation. So if you want to find a node and change its style or attribute or value, bepis is **NOT** your friend (unless you don't mind clearing the ENTIRE document and writing everything again, then ... bepis *would be* your friend).


## Roadmap

- Make parser better (it's [#1](an adhoc nightmare currently) but it works for the simple cases I need)
- Create a HTML -> bepis converter, so you can take any HTML and convert it into a bepis script (just for fun and sort of as a way to test)
- Make bepis friendly for the server (so replace `document.createElement` and associated Element API calls with more text based stuff).

## RoadNOTmap

- Anything to do with dynamic updating HTML, components, element location pinning, or anything at all like that. THer'es plenty of good tools for that, so take your pick and take it elsehwere if that's your need.
- ANything to do with state management or anything esoteric and highfalutin and ennobled like that. Bepis is just for HTML + CSS (and maybe some event listeners) but nothing about updating (*it's just a better way to write HTML*)

## Related Projects

I don't know. I didn't search any "prior art." Let me know how I reinvented this tiny misshapen wheel by opening a PR request.


----------


<p align=center>
  <img src="readme-images/bepiswatnsyou.jpg?raw=true" alt="Bepis Wants You" width="80%">
</p>
