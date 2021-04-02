# Dax code used in PowerBI report

<a href="red">**crossfilesalesandstock =</a>
CALCULATE (
    SUM ( 'ciurrent stock'[stockss] ),
    CROSSFILTER ( '1-Sales Details'[STORE], 'Complete Shop Details'[Sotre Name], BOTH )
)



<span style="color:blue">some *This is Blue italic.* text</span>

<span style="color:red">some **This is Red Bold.** text</span>

ome Markdown text with <span style="color:blue">some *blue* text</span>.

<p>Some Markdown text with <span style="color:blue">some <em>blue</em> text</span>.</p>

// resets
s { text-decoration:none; } //strike-through
em { font-style: normal; font-weight: bold; } //italic emphasis


// colors
s { color: green }
em { color: blue }

~~This is green~~
_this is blue_

<font color='red'>test blue color font</font>

$\color{color-code}{your-text-here}$

This is <span style="color: red">written in red</span>

This is *red*{: style="color: red"}

This is a paragraph that for some reason we want blue.
{: .blue}

#### A blue heading
{: .blue}

A blue and bold paragraph.
{: .blue .bold}

#### A blue heading
{: .blue #blue-h}

<h4 class="blue" id="blue-h">A blue heading</h4>

<strong style="color: red; opacity: 0.80;">My Bold Text, in red color.</strong>

**My Bold Text, in red color.**{: style="color: red; opacity: 0.80;" }

a[href='red'] {
    color: red;
    pointer-events: none;
    cursor: default;
    text-decoration: none;
}
<a href="red">Look, ma! Red!</a>

<style>
r { color: Red }
o { color: Orange }
g { color: Green }
</style>

# TODOs:

- <r>TODO:</r> Important thing to do
- <o>TODO:</o> Less important thing to do
- <g>DONE:</g> Breath deeply and improve karma

