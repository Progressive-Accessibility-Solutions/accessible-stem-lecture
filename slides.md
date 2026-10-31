***Head

:::Icon Resources/logos/favicon.ico
:::CSS node_modules/normalize.css/normalize.css minify
:::CSS Resources/styles.css minify
:::Script Resources/scripts/mathjax-conf.js minify
:::Script https://cdn.jsdelivr.net/npm/mathjax@4.0.0/tex-mml-svg.js
:::Script Resources/scripts/diagcess.js
:::Script Resources/scripts/diagcess-conf.js minify
:::Script Resources/scripts/general-conf.js minify
:::

***

***TitleSlide

:::Title Creating Accessible STEM Learning Resources
:::Subtitle From Markdown to HTML, Mathematics and Interactive Diagrams
:::

*******************

## Today's Journey

How is educational content **created, represented, converted and accessed**?

* Document formats (10 min)
* HTML (10 min)
* Markdown (10 min)
* Mathematics with LaTeX (10 min)
* Diagrams with PreFigure (15 min)
* Putting it all together (5 min)

## The Central Idea

**Write content in a structured way, represent mathematics and diagrams meaningfully, and deliver everything in an accessible format that students can use with their existing devices and assistive technologies.**

* This is **not** a programming class
* Goal: understand the formats and know how you can create or contribute accessible STEM content

## Part 1: Understanding Document Formats

What happens when we

* write a chapter in Microsoft Word,
* save it as a PDF, or
* open a website in Chrome?

**Are these all the same kind of document?**

## DOCX and PDF

**DOCX – Microsoft Word** (`.docx`)

* Designed for authoring and editing
* Headings, paragraphs, tables, images, equations
* Accessible *when correctly structured*

**PDF – Portable Document Format** (`.pdf`)

* Designed to preserve appearance and layout
* May have selectable text, tags, links and maths – or be just scanned images
* Accessibility depends on internal structure and tagging

## Markdown, HTML and EPUB

**Markdown** (`.md`) – lightweight markup written in plain text

* Easy to write, read and maintain; converts to HTML, PDF, DOCX, EPUB

**HTML** (`.html`) – the standard language for web content

* Semantic structure; opens directly in any web browser

**EPUB** (`.epub`) – packaged web content for digital books

* Structured HTML, CSS, images, navigation; reflowable text; MathML and SVG

## The Important Comparison

| Format   | Main purpose              | Accessibility potential     |
| -------- | ------------------------- | --------------------------- |
| DOCX     | Create and edit documents | High, with proper structure |
| PDF      | Preserve document layout  | High if properly tagged     |
| Markdown | Author structured content | Depends on conversion       |
| HTML     | Structure web content     | Very high                   |
| EPUB     | Distribute digital books  | Very high                   |

**A file extension does not guarantee accessibility.**

## The Content Creation Pipeline

Markdown can be our common **authoring source** – not the universal format of every document.

```
              Markdown (.md)
                    |
        conversion and publishing tools
      /        |           |          \
   HTML      EPUB        DOCX        PDF
   web     textbook    editable    printable
```

* Each output needs suitable conversion, accessibility features and validation
* Complex mathematics and diagrams need dedicated processing

## Part 2: What Is HTML?

When you open Google, YouTube, Wikipedia or an online newspaper – **what are you actually viewing?**

* HTML content, displayed by a web browser
* **H**yper**T**ext **M**arkup **L**anguage – the standard language for structuring web content
* Websites, online articles, learning platforms, digital textbooks, online exams
* We use it every day, even if we never see the source

## Three Technologies, Three Responsibilities

| Technology | Responsibility              | Analogy                 |
| ---------- | --------------------------- | ----------------------- |
| HTML       | Structure and meaning       | Building structure      |
| CSS        | Appearance and presentation | Paint and decoration    |
| JavaScript | Behaviour and interaction   | Controls and mechanisms |

In a textbook chapter:

* HTML says "this is a heading / paragraph / equation / table / diagram"
* CSS controls fonts, spacing, colours, layout
* JavaScript enables exploration of maths and diagrams

## What Does HTML Look Like?

```
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Mathematics Chapter</title>
</head>
<body>
  <h1>Introduction to Geometry</h1>
  <h2>Triangles</h2>
  <p>A triangle has three sides.</p>
  <ul>
    <li>Equilateral triangle</li>
    <li>Isosceles triangle</li>
  </ul>
</body>
</html>
```

## The Important Tags

* `<h1>` – main heading; `<h2>` – subheading
* `<p>` – paragraph
* `<ul>` – unordered list; `<li>` – list item

The browser interprets the tags and displays structured content. **A screen reader uses the same structure** to let students jump by heading, list or table.

## One HTML Document Can Contain

* **Text** – headings, paragraphs, lists, tables, links
* **Mathematics** – MathML expressions
* **Diagrams** – SVG graphs, charts, illustrations
* **Interaction** – JavaScript navigation, exploration, feedback

**HTML provides the structure, SVG and MathML represent the content, CSS controls presentation, JavaScript adds behaviour.**

## Mathematics in HTML: MathML

Structured mathematics – not an image of an equation:

```
<math xmlns="http://www.w3.org/1998/Math/MathML">
  <mfrac>
    <mrow><mi>x</mi><mo>+</mo><mn>2</mn></mrow>
    <mn>3</mn>
  </mfrac>
  <mo>=</mo><mn>5</mn>
</math>
```

* `<mfrac>` fraction, `<mrow>` group, `<mi>` variable, `<mn>` number, `<mo>` operator

## Diagrams in HTML: SVG

* Vector format – scales without losing quality
* Made of **objects**: a triangle is three lines, three vertices, three labels – not one flat picture
* Supports text descriptions and accessible labels
* Components can be interactive and navigable with assistive technology – *when properly authored*

## Why Is HTML Portable?

* Opens in Chrome, Edge, Firefox, Safari – no special reader needed
* Works on laptop, desktop and supported mobile devices
* Works **offline** if CSS, JavaScript, fonts and images are bundled locally
* Caveats: some browsers restrict local JavaScript; externally hosted libraries need internet

**Demo:** open one HTML chapter in Chrome and navigate it with NVDA – headings, lists, mathematics, diagrams.

## Part 3: Markdown – Writing the Content

**Do teachers need to learn HTML to create accessible content?**

Not necessarily.

* Markdown: structured content using ordinary text and a few symbols
* The source stays readable even before conversion

## Markdown Source versus Rendered Output

```
# Geometry

## Triangles

A triangle has three sides.

- Equilateral
- Isosceles
- Scalene
```

Renders as a level 1 heading "Geometry", a level 2 heading "Triangles", a paragraph and a bulleted list.

## Markdown Basics (1)

```
# Chapter 1: Mathematics
## Algebra
### Linear Equations
```
Number of `#` = heading level.

```
A triangle is a polygon with three sides.

It has three vertices and three interior angles.
```
A blank line separates paragraphs.

```
This is **important information**.   This is *emphasised text*.
```

## Markdown Basics (2)

```
Types of triangles:

- Equilateral triangle
- Isosceles triangle

Steps to solve an equation:

1. Identify the variable.
2. Simplify both sides.
3. Isolate the variable.
```

```
[Open Wikipedia](https://www.wikipedia.org/)
```

## Images and Tables

```
![A triangle with vertices A, B and C](triangle.svg)
```

Alternative text states the image's purpose – but **complex diagrams need more than a short alt text**.

```
| Triangle    | Number of equal sides |
|-------------|----------------------:|
| Equilateral | 3                     |
| Isosceles   | 2                     |
| Scalene     | 0                     |
```

## Mathematics in Markdown

```
Inline equation: $x + 2 = 5$

Display equation:

$$
\frac{x+2}{3}=5
$$
```

Inline: $x + 2 = 5$. Display:

$$\frac{x+2}{3}=5$$

Maths in Markdown is an extension (e.g. Pandoc), not part of basic CommonMark.

## A Complete Markdown Chapter

```
# Chapter 1: Mathematics

## Linear Equations

A linear equation is an equation in which the
highest power of the variable is one.

### Example
Solve:

$$
x + 2 = 5
$$

**Solution**

1. Subtract 2 from both sides.
2. Therefore, x = 3.
```

## Converting with Pandoc

[Pandoc](https://pandoc.org) converts between Markdown, HTML, DOCX, EPUB, PDF and more.

```
pandoc chapter.md -o chapter.html
pandoc chapter.md -o chapter.docx
pandoc chapter.md -o chapter.epub
pandoc chapter.md -o chapter.pdf
```

* PDF generation needs a PDF engine
* **Teachers concentrate on writing structured content – not on designing every output document**

## Part 4: Mathematics with LaTeX

**How do we write mathematics so that computers can understand, render and speak it?**

* LaTeX: a document preparation system widely used for mathematics and science
* Its notation is also used by MathJax
* A convenient way to *author* mathematics

## Basic LaTeX

| Concept     | Rendered                  |
| ----------- | ------------------------- |
| Addition    | $x + y$                   |
| Fraction    | $\frac{a}{b}$             |
| Power       | $x^2$                     |
| Square root | $\sqrt{x}$                |
| Summation   | $\sum_{i=1}^{n} i$        |
| Integral    | $\int_0^1 x^2 \\, dx$     |

## The Same, as LaTeX Source

```
x + y
\frac{a}{b}
x^{2}
\sqrt{x}
\sum_{i=1}^{n} i
\int_0^1 x^2 \, dx
\alpha, \beta, \theta, \pi
```

* Fractions: `\frac{numerator}{denominator}`
* Superscripts `^`, subscripts `_`, Greek letters with a backslash

## Matrices

```
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
```

$$\begin{bmatrix} 1 & 2 \\\\ 3 & 4 \end{bmatrix}$$

## From LaTeX to Accessible Mathematics

```
LaTeX source:  \frac{x+2}{3}=5
        |
 MathJax (or a conversion pipeline)
        |
 MathML: structured mathematical expression
        |
 Visual rendering  +  speech  +  Braille
```

* **LaTeX** – authoring
* **MathJax** – JavaScript rendering, with accessibility and navigation
* **MathML** – structure
* **Screen reader + speech rules** – communicate the structure

## Try It: Navigable Mathematics

In this presentation, MathJax is active. Focus the equation and explore it with the keyboard:

$$\frac{x+2}{3}=5$$

$$\int_0^1 x^2 \\, dx = \frac{1}{3}$$

**Rendering an equation visually is not the same as making it accessible. Test its speech and navigation.**

## Part 5: Accessible Diagrams with PreFigure

**How do we make a geometry diagram accessible to someone who cannot see it?**

Conventional approach:

* Draw in software, export PNG or JPEG
* Insert into the textbook, add alternative text

But how does a student explore the individual sides, vertices, angles and relationships? **An image alone cannot offer that.**

## What Is PreFigure?

[PreFigure](https://prefigure.org) is an authoring system for mathematical diagrams.

**Describe the mathematical meaning and structure of a diagram – not just its visual appearance.**

From one source it generates:

* SVG diagrams for digital publications
* Annotations for screen-reader navigation
* Tactile diagrams

## PreFigure Source: XML

The publicly documented PreFigure format is **XML**:

```
<diagram dimensions="(300,300)" margins="5">
  <definition> f(x) = exp(x/3)*cos(x) </definition>
  <definition> a = 1 </definition>
  <coordinates bbox="(-4,-4,4,4)">
    <grid-axes xlabel="x" ylabel="y"/>
    <graph function="f"/>
    <tangent-line function="f" point="a"/>
    <point p="(a,f(a))"><m>(a,f(a))</m></point>
  </coordinates>
</diagram>
```

## Reading the Source

| Element         | Purpose                                       |
| --------------- | --------------------------------------------- |
| `<diagram>`     | The diagram and its drawing area              |
| `<definition>`  | Defines expressions or variables              |
| `<coordinates>` | The coordinate system; `bbox` = visible range |
| `<grid-axes>`   | Coordinate grid and axes                      |
| `<graph>`       | Draws a function                              |
| `<point>`       | Adds a point                                  |
| `<m>`           | Mathematical notation                         |

## From Source to Accessible Diagram

```
PreFigure source (XML)
        |
PreFigure processing
        |
   +----+-----------------+
   |                      |
  SVG                Annotations
  visual             structured exploration
   |                      |
   +----------+-----------+
              |
   Screen-reader navigation  and  tactile production
```

## Example: An Explorable Diagram

:::Diagcess tangent Resources/prefigure/tangent.svg Resources/prefigure/tangent.xml minify
:::

:::Standalone Click or focus on the diagram and press <kbd>A</kbd> to start, <kbd>Up,Down,Left,Right</kbd> to explore, <kbd>Escape</kbd> to quit.
:::

## Demo: The PreFigure Playground

[davidaustinm.github.io/prefigure](https://davidaustinm.github.io/prefigure/)

* Edit a mathematical diagram
* Generate the SVG
* Explore its annotations

Local installation for the interested:

```
pip install prefig
prefig init
prefig build triangle.xml
prefig build -f tactile triangle.xml
```

## What Teachers Should Take Away

1. A diagram is not just a picture – it contains mathematical information
2. Each component has a role and relationships to other components
3. A blind student should be able to explore those components
4. Understanding should not depend entirely on a teacher's verbal explanation
5. One source can serve visual, speech and tactile access

## Part 6: Putting It All Together

An accessible chapter on **Linear Equations and Graphs**:

1. **Text** – Markdown: headings, explanations, examples, exercises
2. **Mathematics** – LaTeX: equations, fractions, matrices
3. **Math structure** – MathML for assistive technology
4. **Diagrams** – PreFigure: axes, functions, points
5. **Visuals** – SVG with annotations
6. **Publication** – HTML combining everything
7. **Distribution** – EPUB / DOCX / PDF, each validated
8. **Testing** – NVDA, VoiceOver, Braille displays, and feedback from blind students

## From Content to Independent Learning

**One source. Multiple representations. Greater accessibility.**

* Markdown for structured content
* LaTeX for mathematical authoring
* MathML for mathematical structure
* PreFigure for accessible diagrams
* SVG for scalable graphics
* HTML for digital delivery; EPUB for digital textbooks

## The Ultimate Goal

Enable blind students to **read, navigate, explore, understand and solve** STEM problems independently.

Don't memorise syntax – recognise the formats, understand what each contributes, and learn enough to create and modify material.

**Progressive Accessibility Foundation – Making Knowledge Boundless**

*Thank you – questions?*
