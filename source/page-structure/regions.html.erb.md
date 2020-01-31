---
title: Page Regions
order: 2
wcag_success_criteria:
  - 1.3.1
  - 2.4.1
  - 2.4.6
wcag_techniques:
  - ARIA11
technologies: HTML5, WAI-ARIA
editors:
- Eric Eggert: "https://www.w3.org/People/yatil/"
- Shadi Abou-Zahra: "https://www.w3.org/People/shadi/"
contributors:
- The Education and Outreach Working Group (<a href="https://www.w3.org/WAI/EO/">EOWG</a>)
support: Developed with support from the <a href="https://www.w3.org/WAI/ACT/">WAI-ACT project</a>, co-funded by the <strong>European Commission <abbr title="Information Society Technologies">IST</abbr> Programme</strong>.
---

Mark up different regions of web pages and applications, so that they can be identified by web browsers and assistive technologies.

## Page header

{::nomarkdown}<%= image_tag 'page-structure-header.png', :alt => '', :class => "symbol" %>{:/nomarkdown} Most websites have a region at the top of every page that contains site-wide information, such as the website logo, search function, and navigation options. HTML5 provides the `<header>` element, which can be used to define such a region.

{::nomarkdown}
<%= notes_start %>
{:/nomarkdown}

**Note:** If the `<header>` element is scoped to the `<body>` element, it is associated with the whole page, but as a descendant element of `<main>` element, a sectioning content element, or a sectioning root element other than `<body>` the `<header>` has no implicit role and is therefore not output by assistive technology.

{::nomarkdown}
<%= notes_end %>
{:/nomarkdown}

{::nomarkdown}
<%= demo :start %>
{:/}

{::nomarkdown}
<%= code_start %>
{:/nomarkdown}

~~~html
<header>
  …
  <img src="/images/logo.png" alt="SpaceBear Inc.">
  …
</header>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

{::nomarkdown}
<%= demo :middle %>
{:/}

View a [complete code example](example.html) for all regions combined.

{::nomarkdown}
<%= demo :end %>
{:/}

## Page footer

{::nomarkdown}<%= image_tag 'page-structure-footer.png', :alt => '', :class => "symbol" %>{:/nomarkdown} Similar to the page header, most websites also have a region at the bottom of every page that contains site-wide information, such as copyright information, privacy statements, or disclaimers. HTML5 provides the `<footer>` element, which can be used to define such a region.

{::nomarkdown}
<%= notes_start %>
{:/nomarkdown}

**Note:** If the `<footer>` element is scoped to the `<body>` element, it is associated with the whole page, but as a descendant element of `<main>` element, a sectioning content element, or a sectioning root element other than `<body>` the `<footer>` has no implicit role and is therefore not output by assistive technology.

{::nomarkdown}
<%= notes_end %>
{:/nomarkdown}

{::nomarkdown}
<%= code_start %>
{:/nomarkdown}

~~~html
<footer>
  …
  <p>&copy; 2014 SpaceBears Inc.</p>
  …
</footer>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

## Navigation

{::nomarkdown}
<%= ref :start %>
{:/nomarkdown}

{::nomarkdown}<%= image_tag 'page-structure-navigation.png', :alt => '', :class => "symbol" %>{:/nomarkdown} The HTML5 `<nav>` element can be used to identify a navigation menu. A web page can have any number of navigation menus. Use [labels](labels.html) to identify each navigation menu.

{::nomarkdown}
<%= code_start %>
{:/nomarkdown}

~~~html
<nav aria-label="Main Navigation">
  …
</nav>
…
<nav aria-labelledby="quicknav-heading">
  <h5 id="quicknav-heading">Quick Navigation</h5>
  …
</nav>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

{::nomarkdown}
<%= ref :middle %>
{:/nomarkdown}

The [Menus tutorial](/menus/index.html) provides more details on creating menus.

{::nomarkdown}
<%= ref :end %>
{:/nomarkdown}

## Main content

{::nomarkdown}<%= image_tag 'page-structure-main.png', :alt => '', :class => "symbol" %>{:/nomarkdown} Use the HTML5 `<main>` element to identify the main content region of a web page or application.

{::nomarkdown}
<%= code_start %>
{:/nomarkdown}

~~~html
<main>
  <h1>Stellar launch weekend for the SpaceBear 7!</h1>
  …
</main>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

## Complementary content

{::nomarkdown}<%= image_tag 'page-structure-aside.png', :alt => '', :class => "symbol" %>{:/nomarkdown} Use the HTML5 `<aside>` element to identify regions that support the main content, yet are separate and meaningful sections on their own; For example, a side note explaining or annotating the main content.

{::nomarkdown}
<%= code_start %>
{:/nomarkdown}

~~~html
<aside>
  <h3>Related Articles</h3>
  …
</aside>
~~~

{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

## Page Regions in HTML5 Using WAI-ARIA
{:#accessupport}

{::nomarkdown}
<%= ref :start %>
{:/nomarkdown}

Most current web browsers support the above HTML5 elements and convey the information to assistive technology through the accessibility APIs. However, to maximize compatibility with web browsers and assistive technologies that support WAI-ARIA but do not yet support HTML5, it is currently advisable to use both the HTML5 elements and the corresponding WAI-ARIA roles.

{::nomarkdown}
<%= code_start('', 'Examples in HTML5') %>
{:/nomarkdown}
~~~html
<header role="banner">…</header>
<main role="main">…</main>
<nav role="navigation">…</nav>
<footer role="contentinfo">…</footer>
~~~
{::nomarkdown}
<%= code_end %>
{:/nomarkdown}

{::nomarkdown}
<%= ref :middle %>
{:/nomarkdown}

Explore other WAI-ARIA resources:

* [WAI-ARIA Overview](https://www.w3.org/WAI/intro/aria)
* [Notes on Using ARIA in HTML](https://www.w3.org/TR/aria-in-html/)

{::nomarkdown}
<%= ref :end %>
{:/nomarkdown}

## Page Regions in HTML4 Using WAI-ARIA
{:#accessupport}

If HTML5 cannot be used or if an HTML4 page is retrofitted to improve accessibility, add WAI-ARIA code to `div` elements that function as their HTML5 counterparts, for example:

{::nomarkdown}
<%= code_start('', 'Examples in HTML4') %>
{:/nomarkdown}
~~~html
<div class="header" role="banner">…</div>
<div id="main" role="main">…</div>
<div id="nav" role="navigation">…</div>
<div id="footer" role="contentinfo">…</div>
~~~
{::nomarkdown}
<%= code_end %>
{:/nomarkdown}
