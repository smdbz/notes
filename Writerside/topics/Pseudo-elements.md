# Pseudo-elements

Pseudo-elements help you style a specific part of an element. For example, you can decide to apply styling to only the
first word or line in a given element. First, let’s examine the syntax of a pseudo-element.

## Syntax

```CSS
selector::pseudo-elecment {
property: value;
}
```

It is important to note that pseudo-elements use two colons (::) characters.

## Setting up the HTML and CSS files

You can practice the pseudo-elements code blocks below by adding the respective code inside the HTML and CSS files.
Additionally, reference the CSS code in HTML by adding a link tag such as:

`<link rel="stylesheet" href"style.css">`

where **style.css** is the name of your CSS file.

Additionally, add the HTML code inside the `<body>` tag in the HTML file. A sample code block for HTML will appear as
below:

```css
<!DOCTYPE html>

<html>
<head>
  <link rel="stylesheet" href="style.css">
</head>

<body>
    <!-- Add your HTML code here -->
</body>

</html>
```

## ::first-letter

You can use the first-letter pseudo-element to change the colour of just the fidt letter of the three points in the
example text.

```HTML
<!DOCTYPE html> 
<html> 
    <head> 
        <link rel="stylesheet" href="pseudo4.css"> 
    </head> 
<body> 
    <ul> 
        <li>Based in Chicago, Illinois, Little Lemon is a family-owned Mediterranean restaurant, focused on traditional recipes served with a modern twist. </li> 
    <li>The chefs draw inspiration from Italian, Greek, and Turkish culture and have a menu of 12–15 items that they rotate seasonally. The restaurant has a rustic and relaxed atmosphere with moderate prices, making it a popular place for a meal any time of the day.</li> 
    <li>Little Lemon is owned by two Italian brothers, Mario and Adrian, who moved to the United States to pursue their shared dream of owning a restaurant. To craft the menu, Mario relies on family recipes and his experience as a chef in Italy.</li> 
  </ul> 
</body> 
</html> 
```

```CSS
li::first-letter { 

color:coral; 

font-size: 1.3em; 

font-weight: bold; 

line-height: 1; 

}
```


```html
<body>
    <p id="tips"> Don't rinse your pasta after it is drained. </p>
    <p> Slice the tomatoes. Take the extra efforts to seed them. </p>
    <p id="tips"> Peel and seed large tomatoes. </p>
</body>
```

```CSS
#tips::before{
    background: darkkhaki;
    color:darkslategray;
    content: "Tip:";
    padding-left: 3px;
    padding-right: 5px;
    border-radius: 10%;
}

#tips::after{
    background:darkkhaki;
    color:darkslategray;
    content: "!!";
    padding-right: 5px;
    border-radius: 20%;
}
```