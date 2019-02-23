## Fonts

### Font Families

CSS defines five generic font families:

- *Serif fonts*
- *Sans-serif fonts*
- *Monospace fonts*
- *Cursive fonts*
- *Fantasy fonts*

**Specifying a Font Family**

```css
h1 {font-family: Georgia;}
```

the following markup tells a user agent to use Georgia if it’s available, and to use another serif font if it’s not:

```css
h1 {font-family: Georgia, serif;}
```

**Using @font-face**

 @font-face lets you use custom fonts in your designs. While there’s no guarantee that every last user will see the font you want, this feature is very widely supported.

```css
@font-face {
	font-family: "SwitzeraADF";
	src: url("SwitzeraADF-Regular.otf");
}
```

This allows the author to have conforming user agents load the defined .otf file and
use that font to render text when called upon via font-family: SwitzeraADF.



If you want to be sure the user agent understands what kind of font you’re telling it to
use, that can be done with the optional format():

```css
@font-face {
	font-family: "SwitzeraADF";
	src: url("SwitzeraADF-Regular.otf") format("opentype");
}
```



Restricting character range

There is one font descriptor, unicode-range, which has no corresponding CSS property. This descriptor allows authors to define the range of characters to which a custom font can be applied.



### Font Weights

In a fashion very similar to the font-weight keywords bolder and lighter

### Font Size

#### Absolute Sizes

There are seven absolute-size values for font-size: xx-small, x-small, small, medium, large, x-large, and xx-large

#### Relative Sizes

Comparatively speaking, the keywords larger and smaller are simple: they cause the size of an element to be shifted up or down the absolute-size scale, relative to their parent element,

#### Percentages and Sizes

In a way, percentage values are very similar to the relative-size keywords. A percent‐ age value is always computed in terms of whatever size is inherited from an element’s parent.

#### Font Size and Inheritance

#### Using Length Units

The font-size can be set using any length value. All of the following font-size dec‐ larations should be equivalent:

```css
p.one {font-size: 36pt;} 
p.two {font-size: 3pc;}
p.three {font-size: 0.5in;}
p.four {font-size: 1.27cm;} 
p.five {font-size: 12.7mm;}
```

#### Automatically Adjusting Size

### Font Style

font-style is very simple: it’s used to select between normal text, italic text, and
oblique text. 

### Font Stretching

### Font Kerning

### Font Variants

### Font Features

### The font Property

```css
h2 {font: bold normal italic 24px Verdana, Helvetica, Arial, sans-serif;}
```

### Font Matching

