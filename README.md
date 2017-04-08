# GreetrJS - v0.0.1
Simple tiny JS library in order to output personal greetings by language, including jQuery usage. 

## Background

As part of JS course, we need to learn the jQuery code base structure and to build library using similar methods.

So, this specific project isn't a biggest library ever, but it's a great boilerplate in order to build good, safe and usable standalone library or jQuery plugin.


## Initialization

```js
G$(firstName, lastName, language);
```
Defaults: 

firstName, lastName = empty

language = en (english) 


## Basic Functionality

```js
G$('John', 'Doe').greet();
```
Output:
<code>Hello, John!</code>

```js
G$('John', 'Doe').greet(true);
```
Output: 
<code>Greetings, John Doe</code>

```js
G$('John', 'Doe').setLang('es').greet(true);
```
Output: 
<code>Saludos, John Doe</code>

```js
G$('John', 'Doe').log();
```
Output: 
<code>Logged In: John Doe</code>


## Full Example

```js
G$('John', 'Doe').greet().greet(true).setLang('es').log();
```
Outout:</br>
<code>
Hello John!
</code></br>
<code>
Greetings, John Doe
</code></br>
<code>
Inicio sesion: John Doe
</code>


## Error handling

```js
G$('John', 'Doe').setLang('fr');
```
Output: </br>
<code>Error: Uncaught Invalid Language</code>


## Using jQuery (example)</h2>

HTML file:
```HTML
<div id="logindiv">
  <select id="lang">
    <option value="en">English</option>
    <option value="es">Spanish</option>
  </select>
  <input type="button" value="Login" id="login" />
</div>
<h1 id='greeting'></h1>    

<script type="text/javascript" src="jquery-3.1.1.js"></script>
<script type="text/javascript" src="greetr.js"></script>
<script type="text/javascript" src="app.js"></script>
```

app.js file (initializing jQuery):
```JS
$('#login').click(function(){
	var loginGrtr = G$('John', 'Doe');
	loginGrtr.setLang($('#lang').val()).HTMLGreeting('#greeting', true).log();
});
```

