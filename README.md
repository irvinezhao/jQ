# jQuery learn note
## Remove Elements/Content
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

## Filter the Elements to be Removed
The jQuery remove() method also accepts one parameter, which allows you to filter the elements to be removed.

The parameter can be any of the jQuery selector syntaxes.

## jQuery Manipulating CSS
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
