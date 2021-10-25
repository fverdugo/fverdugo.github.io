
<!--
Add here global page variables to use throughout your website.
-->
+++
author = "Francesc Verdugo"
mintoclevel = 2

# Add here files or directories that should be ignored by Franklin, otherwise
# these files might be copied and, if markdown, processed by Franklin which
# you might not want. Indicate directories by ending the name with a `/`.
# Base files such as LICENSE.md and README.md are ignored by default.
ignore = ["node_modules/"]

# RSS (the website_{title, descr, url} must be defined to get RSS)
generate_rss = true
website_title = "Francesc Verdugo website"
website_descr = "Personal webpage and research portfolio by Francesc Verdugo"
website_url   = "https://francescverdugo.com"
+++

<!--
Add here global latex commands to use throughout your pages.
-->
\newcommand{\R}{\mathbb R}
\newcommand{\scal}[1]{\langle #1 \rangle}
\newcommand{\doi}[1]{[DOI:#1](https://dx.doi.org/#1)}
