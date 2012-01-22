Twipsy
===========

This is a port of [Twitters twipsy for Bootstrap](http://twitter.github.com/bootstrap/javascript.html#twipsy) to [mootools](http://mootools.net/). It includes all features of the original, including a Twipsy object for custom integration and all styles are injected via the script, so no additional stylesheet is required.

![Screenshot](http://www.garfieldius.net/external/github/twipsy/screen.png)

How to use
----------

Include the Twipsy.js and call `.twipsy` for an `Element` of an `Elements` collection of your choice.

<pre>```javascript
window.addEvent("domready", function() {
	$$("a.twipsy").twipsy();
});
```</pre>

Options can be passed along by (they are read in the following order)
* Changing the values in Twipsy.defaults
* Passing an object to the `.twipsy` method or the `new Twipsy()` constructor
* Adding `data-` properties to the elements you want to `twipsify`

Example
<pre>```javascript
Twipsy.default.offset = 10
window.addEvent("domready", function() {
	$$("a.twipsy").twipsy({
		"placement": "left"
	});
});
```</pre>

<pre>```html
<a
	class="twipsy"
	title="Show me on the left, with delay"
	data-delay-in="200"
	data-delay-out="200"
	href="#">Show</a>
```</pre>

As you can see, the data attributes use hyphens in case the option value is camelCased.


Options
----------
<table>
	<tr>
		<th>Name</th>
		<th>Type</th>
		<th>Default</th>
		<th>Description</th>
	</tr>
	<tr>
		<td>animate</td>
		<td>boolean</td>
		<td>true</td>
		<td>apply a css fade transition to the tooltip</td>
	</tr>
	<tr>
		<td>delayIn</td>
		<td>number</td>
		<td>0</td>
		<td>delay before showing tooltip (ms)</td>
	</tr>
	<tr>
		<td>delayOut</td>
		<td>number</td>
		<td>0</td>
		<td>delay before hiding tooltip (ms)</td>
	</tr>
	<tr>
		<td>fallback</td>
		<td>string</td>
		<td>''</td>
		<td>text to use when no tooltip title is present</td>
	</tr>
	<tr>
		<td>placement</td>
		<td>string</td>
		<td>'above'</td>
		<td>how to position the tooltip - above | below | left | right
		</td>
	</tr>
	<tr>
		<td>html</td>
		<td>boolean</td>
		<td>false</td>
		<td>allows html content within tooltip</td>
	</tr>
	<tr>
		<td>offset</td>
		<td>number</td>
		<td>0</td>
		<td>pixel offset of tooltip from target element</td>
	</tr>
	<tr>
		<td>title</td>
		<td>string, function</td>
		<td>'title'</td>
		<td>attribute or method for retrieving title text</td>
	</tr>
	<tr>
		<td>trigger</td>
		<td>string</td>
		<td>'hover'</td>
		<td>how tooltip is triggered - hover | focus | manual</td>
	</tr>
	<tr>
		<td>template</td>
		<td>string</td>
		<td>[default markup]</td>
		<td>The html template used for rendering a twipsy.</td>
	</tr>
	<tr>
		<td>injectStyles</td>
		<td>boolean</td>
		<td>true</td>
		<td>Inject the default styles. Useful if you need a ready and go solution for twipsies. In case you want to use your own styles, set this to false. eg:<br><pre>
Twipsy.defaults.injectStyles = false;
window.addEvent("domready", function() {
  $$("a.twipsy").twipsy();
});
		</pre></td>
	</tr>
</table>

Styles
----------
If you implement your own styles by setting `injectStyles` to false, keep all definitions that are required for Twipsy to function properly. You also have to keep the selectors.
Those are the default styles. Just copy and adjust to your needs:

```css
.twipsy {
	display: block;
	position: absolute;
	visibility: visible;
	padding: 5px;
	font-size: 11px;
	z-index: 1000;
	filter: alpha(opacity = 80);
	-khtml-opacity: 0.8;
	-moz-opacity: 0.8;
	opacity: 0.8;
}
.twipsy-fade {
	-webkit-transition: opacity 0.15s linear;
	-moz-transition: opacity 0.15s linear;
	-ms-transition: opacity 0.15s linear;
	-o-transition: opacity 0.15s linear;
	transition: opacity 0.15s linear;
	opacity: 0;
}
.twipsy.twipsy-fade.twipsy-in {
	filter: alpha(opacity = 80);
	-khtml-opacity: 0.8;
	-moz-opacity: 0.8;
	opacity: 0.8;
}
.twipsy.above .twipsy-arrow {
	bottom: 0;
	left: 50%;
	margin-left: -5px;
	border-left: 5px solid transparent;
	border-right: 5px solid transparent;
	border-top: 5px solid #000000;
}
.twipsy.left .twipsy-arrow {
	top: 50%;
	right: 0;
	margin-top: -5px;
	border-top: 5px solid transparent;
	border-bottom: 5px solid transparent;
	border-left: 5px solid #000000;
}
.twipsy.below .twipsy-arrow {
	top: 0;
	left: 50%;
	margin-left: -5px;
	border-left: 5px solid transparent;
	border-right: 5px solid transparent;
	border-bottom: 5px solid #000000;
}
.twipsy.right .twipsy-arrow {
	top: 50%;
	left: 0;
	margin-top: -5px;
	border-top: 5px solid transparent;
	border-bottom: 5px solid transparent;
	border-right: 5px solid #000000;
}
.twipsy-inner {
	padding: 3px 8px;
	background-color: #000000;
	color: white;
	text-align: center;
	max-width: 200px;
	text-decoration: none;
	-webkit-border-radius: 4px;
	-moz-border-radius: 4px;
	border-radius: 4px;
}
.twipsy-arrow {
	position: absolute;
	width: 0;
	height: 0;
}
```


Credits
----------
* Jason Frame for the original Twipsy script
* Twitter Inc. for the improved Twipsy


License
----------

[Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)
