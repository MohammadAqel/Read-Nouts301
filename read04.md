#   Grid

grid is a way for layout systems in css
### container div
`display:grid` generates a block-level grid

`display:inline-grid` generates an inline-level grid

` grid-template-columns and rows`to add the number of rows and columns and it's track-size (can be length or using fr unit) and the line name

* fr unit :allows you to set the size of a track as a fraction of the free space `1fr 2fr`

`grid-template-areas` defines a grid template by the name ,(.)=an empty grid ,(none) no grid areas are defined

`grid-template` shorthand for setting grid-template-rows, grid-template-columns, and grid-template-areas in a single declaration.
```
.container {
  grid-template-rows: [row1-start] 25px [row1-end row2-start] 25px [row2-end];
  grid-template-columns: auto 50px auto;
  grid-template-areas: 
    "header header header" 
    "footer footer footer";
}
```
 `grid-column-cap` and row gives some margin between different grid items

 `justify-items` aligns grid items along the inline (row) axis

 `align-items` aligns grid items along the block (column) axis

 `place-items` put `<align-items>` / `<justify-items>`  in a single declaration

 `place-content` ets both the align-content and justify-content properties in a single declaration

### items div
`grid-column-start`
`grid-column-end`
`grid-row-start`
`grid-row-end` , determines a grid item’s location within the grid by referring to specific grid lines

`grid-area` Gives an item a name so that it can be referenced by a template created with the 

`grid-template-areas` property
`justify-self` aligns item inside a cell along the inline (row)
`align-self` aligns item inside  a cell along the block (column)

# Regular expressions (regex)

* Regex's are are extremely useful in extracting information from any text by searching for one or more matches of a specific search pattern like ASCII or Unicode

* this syntax cover all programming languages

```
^The        matches any string that starts with The -> Try it!
end$        matches a string that ends with end
^The end$   exact string match (starts and ends with The end)
roar        matches any string that has the text roar in it

abc*        matches a string that has ab followed by zero or more c -> Try it!
abc+        matches a string that has ab followed by one or more c
abc?        matches a string that has ab followed by zero or one c
abc{2}      matches a string that has ab followed by 2 c
abc{2,}     matches a string that has ab followed by 2 or more c
abc{2,5}    matches a string that has ab followed by 2 up to 5 c
a(bc)*      matches a string that has a followed by zero or more copies of the sequence bc
a(bc){2,5}  matches a string that has a followed by 2 up to 5 copies of the sequence bc


```
and theres a lot of operator like (OR operator — | or []),(Character classes — \d \w \s and ),(Grouping and capturing — ()) etc..

* This operator is very useful when we need to extract information from strings or data using your preferred programming language