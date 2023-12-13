## the DOM:

#### process of structuring the DOM:

- HTML is received
- HTML tags are converted to tokens
- Tokens are converted to Nodes
- Nodes are converted to the DOM

-When you request a website, no matter what backend language is powering that website, it will respond with HTML. The browser receives a stream of HTML. The bytes are run through a complicated (but fully documented) parsing process that determines the different characters (e.g. the start tag character `<`, an attribute like `href`,

 a closing angle bracket like `>`). After parsing has occurred, a process called **tokenization** begins.

-Tokenization takes one character at a time and builds up **tokens**. The tokens are:

- DOCTYPE

- start tag

- end tag

- comment

- character

- end-of-file

-At this state, the browser has received the bytes that've been sent by a server. The browser has converted the bytes to tags and has read through the tags to create a list of tokens.

This list of tokens then goes through the tree construction stage. The output of this stage is a tree-like structure - this is the DOM!

-I want to point out two important quotes that Illya said in the video:

> **a tree structure that captures the content and properties of the HTML and all the relationships between the nodes**

> **the DOM is the full, parsed representation of the HTML**

So **the DOM** is a model (representation) of the relationships and attributes of the HTML document that was received. Remember that DOM stands for "Document Object Model". Something that I've found to be true as I've been learning is that to break something down, just read the thing backwards:

Document Object Model

...would become…

Object Model of the Document!

Remember that a JavaScript object is a tree-like structure that has properties and values. So the DOM can be accessed using a special object provided by the browser: `document`

Try this:

1. open the console on this page
2. type out the word `document`
   - careful not to declare it (`const document`)
   - careful not to wrap it in quotes (`"document"`)
3. press enter

![A Screenshot viewing the `document` object in the DevTools' Console pane.](https://video.udacity-data.com/topher/2017/December/5a22336a_ud117-l1-document-object-in-console/ud117-l1-document-object-in-console.jpg)

*Viewing the `document` object in the DevTools' Console pane.*

The `document` object is provided by the browser and is a representation of the HTML document. This object is *not* provided by the JavaScript language. ECMAScript is the language specification that JavaScript is based on, and it only references the document object model in one place, in its "Global Object" section:

> In addition to the properties defined in this specification the global object may have additional host defined properties. This may include a property whose value is the global object itself; for example, in the HTML document object model the window property of the global object is the global object itself. ([source](https://www.ecma-international.org/ecma-262/#sec-global-object))

Basically, this says that the `document` object is not part of JavaScript, but is expected to *already exist* and be freely accessible to JavaScript code.

The DOM is standardized by the W3C. There are a number of specifications that make up the DOM, here are few:

- Core Specification
- Events Specification
- Style Specification
- Validation Specification
- Load and Save Specification

To see the full list of DOM specs, check out the standard at: https://www.w3.org/standards/techs/dom#w3c_all

## Reflect

Ok, so do not scroll back up or review what you just read. Just take a moment, think about everything you've learned about the DOM and the document object and, in your own words, write an explanation of what "the DOM" is.

SUBMIT

## The DOM Recap

The DOM stands for "Document Object Model" and is a tree-like structure that is a representation of the HTML document, the relationship between elements, and contains the content and properties of the elements.

The DOM is *not*:

- **part of the JavaScript language**

The DOM is:

- **constructed from the browser**
- is globally accessible by JavaScript code using the `document` object

### Further Research

- [DOM Introduction](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
- [Section 8.2 Parsing HTML documents](https://www.w3.org/TR/html5/syntax.html#parsing) from the W3C's HTML Documentation
- [DOM Specification](https://www.w3.org/standards/techs/dom#w3c_all) on W3C
- [HTML Document Object Model mentioned in the ECMAScript Specification](https://www.ecma-international.org/ecma-262/#sec-global-object) - the language specification used by JavaScript
