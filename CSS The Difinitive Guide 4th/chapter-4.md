## Values and Units

### Keywords

#### Global keywords

CSS3 defines three “global” keywords that are accepted by every property in the spec‐
ification: inherit, initial, and unset.

#### inherit

It makes the value of a property on an element the same
as the value of that property on its parent element

#### initial

It sets the value of a property to the defined initial value,whicb in a way means it "resets".

#### unset

The keyword unset acts as a universal stand-in for both inherit and ini
tial. If the property is inherited, then unset has the same effect as if inherit was
used. If the property is *not* inherited, then unset has the same effect as if initial was
used.

### Numbers and Percentages

#### Integers

整型数值

#### Numbers

整型或实数

#### Percentages

百分数

#### Fractions

分数

### Distances

All length units can be expressed as either positive or negative numbers followed by a
label, although note that some properties will accept only positive numbers. 

#### Absolute Length Units

- Inches (in)
- *Centimeters (*cm)
- *Millimeters (*mm*)*
- *Quarter-millimeters (*q*)*
- *Points (*pt*)*
- *Picas (*pc*)*
- *Pixels (*px*)*

#### Resolution Units

- *Dots per inch (*dpi*)*
- *Dots per centimeter (*dpcm*)*
- *Dots per pixel unit (*dppx*)*

As of late 2017, these units are only used in the context of media queries. As an example, an author can create a media block to be used only on displays that have higher than 500 dpi: 

**@media** (min-resolution: 500dpi) { */\* rules go here \*/* 

} 

#### Relative Length Units

- em and ex units
- The rem unit
- The ch unit

#### Viewport-relative units

- *Viewport width unit (*vw*)*
- *Viewport height unit (*vh*)*
- *Viewport minimum unit (*vmin*)*
- *Viewport maximum unit (*vmax*)*

### Calculation values

Calc() function

###  Attribute Values

attr() expression.

### Color

- Named Colors

- Colors by RGB and RGBa

  ```
      rgb(100%,100%,100%)
      rgb(0%,0%,0%)
      
      rgba(255,255,255,0.5)
      rgba(100%,100%,100%,0.5)
  ```

- Hexadecimal RGB colors

  ```css
  h1 {color: #FF0000;} 
  h2 {color: #903BC0;} 
  h3 {color: #000000;} 
  h4 {color: #808080;}
  ```

- Colors by HSL and HSLa

- Color Keywords

  There are two special keywords that can be used anywhere a color value is permitted.
  These are transparent and currentColor.

### Angles

- deg  Degrees, of which there are 360 in a full circle.
- grad Gradians, of which there are 400 in a full circle. Also known as *grades* or *gons*.
- rad Radians, of which there are 2π (approximately 6.28) in a full circle.
- turn Turns, of which there is one in a full circle. This unit is mostly useful when ani‐
  mating a rotation and you wish to have it turn multiple times, such as 10turn to
  make it spin 10 times.

### Time and Frequency

```css
a[href] {transition-duration: 2.4s;} 
a[href] {transition-duration: 2400ms;}

h1 {pitch: 128hz;} 
h1 {pitch: 0.128khz;}
```

### Position

### Custom Values

```css
html {
--base-color: #639; --highlight-color: #AEA;
}
h1 {color: var(--base-color);}
h2 {color: var(--highlight-color);}
```

