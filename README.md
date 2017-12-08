# jQuery learn note
DOM = Document Object Model

## jQuery - Get Content and Attributes
### Get Content - text(), html(), and val()
Three simple, but useful, jQuery methods for DOM manipulation are:

text() - Sets or returns the text content of selected elements
html() - Sets or returns the content of selected elements (including HTML markup)
val() - Sets or returns the value of form fields
The following example demonstrates how to get content with the jQuery text() and html() methods:

Example
```
$("#btn1").click(function(){
    alert("Text:" + $("#test").text());
});
$("#btn2").click(function(){
    alert("HTML:" + $("#test").html());
});
```
The following example demonstrates how to get the value of an input field with the jQuery val() method:

Example
```
$("#btn1").click(function(){
    alert("Value:" + $("#test").val());
});
```
### Get Attributes - attr()
The jQuery attr() method is used to get attribute values.

The following example demonstrates how to get the value of the href attribute in a link:

Example
```
$("button").click(function(){
    alert($("#w3s").attr("href"));
});
```
## jQuery - Set Content and Attributes
### Set Content - text(), html(), and val()
We will use the same three methods from the previous page to set content:

text() - Sets or returns the text content of selected elements
html() - Sets or returns the content of selected elements (including HTML markup)
val() - Sets or returns the value of form fields
The following example demonstrates how to set content with the jQuery text(), html(), and val() methods:

Example
```
$("#btn1").click(function(){
    $("#test1").text("Hello world!");
});
$("#btn2").click(function(){
    $("#test2").html("<b>Hello world!</b>");
});
$("#btn3").click(function(){
    $("#test3").val("Dolly Duck");
});
```
### A Callback Function for text(), html(), and val()
All of the three jQuery methods above: text(), html(), and val(), also come with a callback function. The callback function has two parameters: the index of the current element in the list of elements selected and the original (old) value. You then return the string you wish to use as the new value from the function.

The following example demonstrates text() and html() with a callback function:

Example
```
$("#btn1").click(function(){
    $("#test1").text(function(i, origText){
        return "Old text:" + origText + " New text: Hello world!
        (index: " + i + ")"; 
    });
});

$("#btn2").click(function(){
    $("#test2").html(function(i, origText){
        return "Old html:" + origText + " New html: Hello <b>world!</b>
        (index: " + i + ")"; 
    });
});
```

### Set Attributes - attr()
The jQuery attr() method is also used to set/change attribute values.

The following example demonstrates how to change (set) the value of the href attribute in a link:

Example
```
$("button").click(function(){
    $("#w3s").attr("href", "https://www.w3schools.com/jquery");
});
```

The following example demonstrates how to set both the href and title attributes at the same time:

Example
```
$("button").click(function(){
    $("#w3s").attr({
        "href" : "https://www.w3schools.com/jquery",
        "title" : "W3Schools jQuery Tutorial"
    });
});
```
### A Callback Function for attr()
The jQuery method attr(), also come with a callback function. The callback function has two parameters: the index of the current element in the list of elements selected and the original (old) attribute value. You then return the string you wish to use as the new attribute value from the function.

The following example demonstrates attr() with a callback function:

Example
```
$("button").click(function(){
    $("#w3s").attr("href", function(i, origValue){
        return origValue + "/jquery"; 
    });
});
```
## jQuery - Add Elements
### Add New HTML Content
We will look at four jQuery methods that are used to add new content:

append() - Inserts content at the end of the selected elements
prepend() - Inserts content at the beginning of the selected elements
after() - Inserts content after the selected elements
before() - Inserts content before the selected elements
### jQuery append() Method
The jQuery append() method inserts content AT THE END of the selected HTML elements.

Example
```
$("p").append("Some appended text.");
```
### jQuery prepend() Method
The jQuery prepend() method inserts content AT THE BEGINNING of the selected HTML elements.

Example
```
$("p").prepend("Some prepended text.");
```
### Add Several New Elements With append() and prepend()
In both examples above, we have only inserted some text/HTML at the beginning/end of the selected HTML elements.

However, both the append() and prepend() methods can take an infinite number of new elements as parameters. The new elements can be generated with text/HTML (like we have done in the examples above), with jQuery, or with JavaScript code and DOM elements.

In the following example, we create several new elements. The elements are created with text/HTML, jQuery, and JavaScript/DOM. Then we append the new elements to the text with the append() method (this would have worked for prepend() too) :

Example
```
function appendText() {
    var txt1 = "<p>Text.</p>";               // Create element with HTML  
    var txt2 = $("<p></p>").text("Text.");   // Create with jQuery
    var txt3 = document.createElement("p");  // Create with DOM
    txt3.innerHTML = "Text.";
    $("body").append(txt1, txt2, txt3);      // Append the new elements 
}
```
### jQuery after() and before() Methods
The jQuery after() method inserts content AFTER the selected HTML elements.

The jQuery before() method inserts content BEFORE the selected HTML elements.

Example
```
$("img").after("Some text after");

$("img").before("Some text before");
```
### Add Several New Elements With after() and before()
Also, both the after() and before() methods can take an infinite number of new elements as parameters. The new elements can be generated with text/HTML (like we have done in the example above), with jQuery, or with JavaScript code and DOM elements.

In the following example, we create several new elements. The elements are created with text/HTML, jQuery, and JavaScript/DOM. Then we insert the new elements to the text with the after() method (this would have worked for before() too) :

Example
```
function afterText() {
    var txt1 = "<b>I </b>";                    // Create element with HTML  
    var txt2 = $("<i></i>").text("love");     // Create with jQuery
    var txt3 = document.createElement("b");    // Create with DOM
    txt3.innerHTML = "jQuery!";
    $("img").after(txt1, txt2, txt3);          // Insert new elements after <img>
}
```
## jQuery - Remove Elements
### Remove Elements/Content
To remove elements and content, there are mainly two jQuery methods:

remove() - Removes the selected element (and its child elements)
empty() - Removes the child elements from the selected element

### jQuery remove() Method
The jQuery remove() method removes the selected element(s) and its child elements.

Example
```
$("#div1").remove();
```

### jQuery empty() Method
The jQuery empty() method removes the child elements of the selected element(s).

Example
```
$("#div1").empty();
```

### Filter the Elements to be Removed
The jQuery remove() method also accepts one parameter, which allows you to filter the elements to be removed.

The parameter can be any of the jQuery selector syntaxes.

The following example removes all <p> elements with class="test":  

Example
```
$("p").remove(".test");
```

This example removes all <p> elements with class="test" and class="demo":  

Example
```
$("p").remove(".test, .demo");
```

## jQuery - Get and Set CSS Classes
### jQuery Manipulating CSS
jQuery has several methods for CSS manipulation. We will look at the following methods:

addClass() - Adds one or more classes to the selected elements
removeClass() - Removes one or more classes from the selected elements
toggleClass() - Toggles between adding/removing classes from the selected elements
css() - Sets or returns the style attribute

### jQuery addClass() Method
The following example shows how to add class attributes to different elements. Of course you can select multiple elements, when adding classes:

Example
```
$("button").click(function(){
    $("h1, h2, p").addClass("blue");
    $("div").addClass("important");
});
```
You can also specify multiple classes within the addClass() method:

Example
```
$("button").click(function(){
    $("#div1").addClass("important blue");
});
```

### jQuery removeClass() Method
The following example shows how to remove a specific class attribute from different elements:

Example
```
$("button").click(function(){
    $("h1, h2, p").removeClass("blue");
});
```
### jQuery removeClass() Method
The following example shows how to remove a specific class attribute from different elements:

Example
```
$("button").click(function(){
    $("h1, h2, p").removeClass("blue");
});
```

## jQuery css() Method
The css() method sets or returns one or more style properties for the selected elements.
### Return a CSS Property
To return the value of a specified CSS property, use the following syntax:

css("propertyname");
The following example will return the background-color value of the FIRST matched element:

Example
```
$("p").css("background-color");
```
### Set a CSS Property
To set a specified CSS property, use the following syntax:

css("propertyname","value");
The following example will set the background-color value for ALL matched elements:

Example
```
$("p").css("background-color", "yellow");
```

### Set Multiple CSS Properties
To set multiple CSS properties, use the following syntax:

css({"propertyname":"value","propertyname":"value",...});
The following example will set a background-color and a font-size for ALL matched elements:

Example
```
$("p").css({"background-color": "yellow", "font-size": "200%"});
```
## jQuery - Dimensions

### jQuery Dimension Methods
jQuery has several important methods for working with dimensions:

width()
height()
innerWidth()
innerHeight()
outerWidth()
outerHeight()
### jQuery Dimensions
![alt text](https://www.w3schools.com/jquery/img_jquerydim.gif)
### jQuery width() and height() Methods
The width() method sets or returns the width of an element (excludes padding, border and margin).

The height() method sets or returns the height of an element (excludes padding, border and margin).

The following example returns the width and height of a specified <div> element:

Example
```
$("button").click(function(){
    var txt = "";
    txt += "Width:" + $("#div1").width() + "</br>";
    txt += "Height:" + $("#div1").height();
    $("#div1").html(txt);
});
```
### jQuery innerWidth() and innerHeight() Methods
The innerWidth() method returns the width of an element (includes padding).

The innerHeight() method returns the height of an element (includes padding).

The following example returns the inner-width/height of a specified <div> element:

Example
```
$("button").click(function(){
    var txt = "";
    txt += "Inner width:" + $("#div1").innerWidth() + "</br>";
    txt += "Inner height:" + $("#div1").innerHeight();
    $("#div1").html(txt);
});
```
### jQuery outerWidth() and outerHeight() Methods
The outerWidth() method returns the width of an element (includes padding and border).

The outerHeight() method returns the height of an element (includes padding and border).

The following example returns the outer-width/height of a specified <div> element:

Example
```
$("button").click(function(){
    var txt = "";
    txt += "Outer width:" + $("#div1").outerWidth() + "</br>";
    txt += "Outer height:" + $("#div1").outerHeight();
    $("#div1").html(txt);
});
```
The outerWidth(true) method returns the width of an element (includes padding, border, and margin).

The outerHeight(true) method returns the height of an element (includes padding, border, and margin).

Example
```
$("button").click(function(){
    var txt = "";
    txt += "Outer width (+margin):" + $("#div1").outerWidth(true) + "</br>";
    txt += "Outer height (+margin):" + $("#div1").outerHeight(true);
    $("#div1").html(txt);
});
```
### jQuery More width() and height()
The following example returns the width and height of the document (the HTML document) and window (the browser viewport):

Example
```
$("button").click(function(){
    var txt = "";
    txt += "Document width/height:" + $(document).width();
    txt += "x" + $(document).height() + "\n";
    txt += "Window width/height:" + $(window).width();
    txt += "x" + $(window).height();
    alert(txt);
});
```
The following example sets the width and height of a specified <div> element:

Example
```
$("button").click(function(){
    $("#div1").width(500).height(500);
});
```
## jQuery Traversing - Ancestors

### Traversing Up the DOM Tree
Three useful jQuery methods for traversing up the DOM tree are:

parent()
parents()
parentsUntil()
### jQuery parent() Method
The parent() method returns the direct parent element of the selected element.

This method only traverse a single level up the DOM tree.

The following example returns the direct parent element of each <span> elements:

Example
```
$(document).ready(function(){
    $("span").parent();
});
```

### jQuery parents() Method
The parents() method returns all ancestor elements of the selected element, all the way up to the document's root element (<html>).

The following example returns all ancestors of all <span> elements:

Example
```
$(document).ready(function(){
    $("span").parents();
});
```
You can also use an optional parameter to filter the search for ancestors.

The following example returns all ancestors of all <span> elements that are <ul> elements:

Example
```
$(document).ready(function(){
    $("span").parents("ul");
});
```

### jQuery parentsUntil() Method
The parentsUntil() method returns all ancestor elements between two given arguments.

The following example returns all ancestor elements between a <span> and a <div> element:

Example
```
$(document).ready(function(){
    $("span").parentsUntil("div");
});
```
## jQuery Traversing - Descendants
### Traversing Down the DOM Tree
Two useful jQuery methods for traversing down the DOM tree are:

children()
find()
### jQuery children() Method
The children() method returns all direct children of the selected element.

This method only traverse a single level down the DOM tree.

The following example returns all elements that are direct children of each <div> elements:

Example
```
$(document).ready(function(){
    $("div").children();
});
```
You can also use an optional parameter to filter the search for children.

The following example returns all <p> elements with the class name "first", that are direct children of <div>:

Example
```
$(document).ready(function(){
    $("div").children("p.first");
});
```
### jQuery find() Method
The find() method returns descendant elements of the selected element, all the way down to the last descendant.

The following example returns all <span> elements that are descendants of <div>:

Example
```
$(document).ready(function(){
    $("div").find("span");
});
```
The following example returns all descendants of <div>:

Example
```
$(document).ready(function(){
    $("div").find("*");
});
```
