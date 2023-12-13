## The DOM Is Built Incrementally

note to remember:

-When the parser gets to a `<script>` tag, it must wait to download the script file and execute that JavaScript code.

-<u>The inline file will execute faster</u> because **the browser doesn't have to make another network request to fetch the JavaScript file**. But the outcome will be exactly the same for both this inline version and if the HTML had linked to an external JavaScript file.

-----------------------------------------

### problem of (Waiting for page content to load):

-When the parser gets to a `<script>` tag, it must wait to download the script file and execute that JavaScript code.

-This causes a (null error) because it would be like running the following code:

```js
null.style.backgroundColor = 'purple';
```

to solve this problem:

-we moved the JavaScript file down to the bottom of the page.

-or use an event is called the `DOMContentLoaded`

------------

### "DOMContentLoaded" event

```js
document.addEventListener('DOMContentLoaded', function () {
    console.log('the DOM is ready to be interacted with!');
});
```

<img title="" src="https://video.udacity-data.com/topher/2017/December/5a2eee37_ud117-domcontentloaded-event-with-indicators/ud117-domcontentloaded-event-with-indicators.jpg" alt="A Screenshot showing the Network pane of DevTools with the DOMContentLoaded indicators highlighted." width="723">

very important !!!!!!!!!!!:

-The target of the `DOMContentLoaded` event is **the `document` objec**t.
