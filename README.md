# A solution for writing visually with ease

It's not difficult to find sources claiming that visual argument can convey a point more clearly, efficiently, and convincingly than freeform text. [The reason is straightforward:](https://www.eyeqinsights.com/power-visual-content-images-vs-text/)

> Visual content reaches an individual’s brain in a faster and more understandable way than textual information. Or, more accurately, a person’s brain is hardwired to recognize and make sense of visual information more efficiently.

One presenter laid out a spectrum of textual->visual like this:

+ **Free-form text**: Think a paper you wrote for a class. It's just plain text and punctuation. Everything is the same font size.
+ **Structured text**: Think a blog article. There will be some headings.
+ **Bullet points**: For a portion of the document, bullets (or numbers) are used to say "these three items are of like-kind, presented for the same purpose." Markdown like we have in github-flavored markdown is great for making content up to this complex.
+ **Tabular formats**: This is something you often see in consulting slides. It's the focus of this repo. One example would be a first row with three points, follwed by more detail on each point in the rows following.
+ **Graphical formats**: For use with numeric data, even very large quantities. Line graphs, bar graphs, heatmaps, etc.

Markdown has given us a simple system for creating documents that contain everything up to bullet points, and also supports image imports. There is also a great deal of development going on right now to make graphical formats easier to produce. However, there is no solution that makes expressing ideas in tabular format simple yet powerful. Enter concept-markdown.

# Goals of concept-markdown

+ < 2 minutes to make your first table
+ Resulting html-based tables are simple yet powerful
+ Plaintext looks like the resulting table
+ Captures the only fundamental uses of tables for making arguments
+ Users can borrow, create, and share their own format sets within well-defined boundaries

### 2 minutes to learn

This is really the main point. What makes markdown wonderful is that it took me ~5 minutes to copy others' work and learn how markdown works and from that point on I could easily create documents that were elegant but seemed like they would be hard to make.

### Tables are simple yet powerful

Concept-markdown minimizes the unecessary bells and whistles. You can do so much with html, but we only want to do a very small range of things. However, we need to end up creating tables that pack all the punch of any table out there.

### Plaintext looks fine on its own

This is what markdown is all about. You can easily read a markdown file without converting it to html and get all the same content. With tables it requires purposeful whitespace but other than that we should be able to do it.

### Capture the fundamental purposes of tables

Tabular format allows us to perform these essential tasks:

+ Show that items are parallel
  + Show a difference between parallel items
+ Provide deeper levels of detail on a particular item
+ Show directional relationships between items

### Make your own formats

Concept-markdown is appropriate for blogs, consulting materials, ebooks, emails, marketing materials, and article/social media comments. Different parties may want to apply their own brand to the tables, and that should be easy to perform by allowing them to import some of their own style elements. This will, however, require extensive security controls.

# Usage

There are three features that concept-md adds to tables:

+ Emphasis to cells
+ Merging of adjacent cells
+ Arrows between cells or as part of the cell

The following table

```
|>===========>|>===========>|>===========>|
|     2016    |     2017    |     2018    |
|-------------|-------------|-------------|
| 2016 item 1 | 2017 item 1 | 2018 item 1 |
|-------------|-------------|-------------|
| 2016 item 2 | 2017 item 2 | 2018 item 2 |
|~~~~~~~~~~~~~X~~~~~~~~~~~~~X~~~~~~~~~~~~~|
|          Concluding statement           |
|https://raw.githubusercontent.com/ptfmiller/concept-md/master/concept-md.css|
```

Is rendered as: (insert screenshot)

Here's a more complex table showing more of the capabilities:
```
|--------------------------|~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|
|                          |        Column title 1         |            Column title 2                   |
|=========================>|---------------------------  ->|---------------------------------------------|
|      A 3-row arrow       |      This item leads to       |  *This bold item* (use markdown internally) |
|XXXXXXXXXXXXXXXXXXXXXXXXXX|-------------------------------X---------------------------------------------|
|                          |  These two columns are joined together and use escape to print a pipe: \|   |
|XXXXXXXXXXXXXXXXXXXXXXXXXX|^-----------------------------:|:---^---------------------------------------:|
|                          | Aligned right and pointing up | Justified and pointing up with a long arrow |
|_________________________>|>=============================>|>============================================|
| De-emphasized arrow item | Emphasized continuation item  |       Emphasized receiving item             |
|------------https://raw.githubusercontent.com/ptfmiller/concept-md/master/concept-md.css----------------|
```
This renders to: (insert screenshot)

The structure of the markdown is pairs of lines. The first line specifies structure of the cells and the second specifies the contents. The bottom row is optional and allows the author to specify a style file to replace the defaults. 

The structure rows consist of **delimiters** `X` or `|` separated by **cell styling information** `=`, `_`, `+`, `-`, `XX`, `:`, `>`, `<`, `V`, and `^`. All other characters are ignored.

The content rows consist of the text that will occupy the cells, separated by `|` delimiters.

### Delimiters

+ `|`: this is the standard delimiter and marks the boundary between two cells' styling.
+ `X`: this is delimiter indicates that two horizontally-adjacent cells will be merged. The engine will look for one fewer cell of content on the next line.

### Cell styling

+ `=`: Strongest emphasis on a cell
+ `_`: Second-strongest emphasis on a cell. Suggested for de-emphasis among similar elements
+ `~`: Light emphasis on a cell. Good as a header.
+ `-`: Standard cell with no emphasis
+ `XX`: Indicate that this cell should be merged with the cell above. You can write additional X's to fill space--they will be ignored.
+ `:`: Alignment indicator. Text will be aligned left if this occurs immediately after the starting delimiter, right if it occurs immediately before the ending delimiter, justified if both, and centered if it is absent.
+ `>`, `<`, `V`, and `^`: Insert arrows. 
  + Arrows with no `-` tails will shape the cell itself, but can only apply to emphasis and strong emphasis cells. These types of arrows are indicated right after the starting delimiter of a cell (to affect the left and top sides of the cell) and right before the ending delimiter of a cell (to affect the right and bottom sides of a cell)
  + Arrows with a `-` tail will insert an arrow image between cells. There are three lengths of each directional arrow, and the length corresponds to the number of `-` characters coming before (or after in the case of `<` arrows) the arrow indicator. The arrow will be assumed to be pointing outward, away from the cell, and will be placed accordingly, unless: 
    + For right and down arrows, the indicator comes right after the starting delimiter of the cell (or after the `:` indicator if there is alignment specified)
    + For left and up arrows, the indicators comes right before the starting delimiter of the cell (or before the `:` indicator if there is alignment specified)

# Remaining challenges

### Approach for getting the engine integrated into mainstream services

+ GFM
+ Wordpress

### Find a good implementation host for the meantime

### Nail down the name

Some alternatives:

+ Slide-down
+ Mark-slide

### See the issues

