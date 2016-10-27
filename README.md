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

*under development*

# Remaining challenges

### Approach for getting the engine integrated into mainstream services

+ GFM
+ Wordpress

### Nail down the name

Some alternatives:

+ Slide-down
+ Mark-slide

### See the issues

