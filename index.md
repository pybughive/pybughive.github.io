---
layout: default
---
<div id="btn_box">
          <a href="{{ site.home_link }}"><button class="btn active"><i class="fa fa-home"></i> Home</button></a>
          <a href="{{ site.pdf_link }}"><button class="btn"><i class="fa fa-file"></i> PDF</button></a>
          <a href="{{ site.github_link }}"><button class="btn"><i class="fa fa-github"></i> GitHub</button></a>
          <a href="{{ site.download_link }}"><button class="btn"><i class="fa fa-download"></i> Download </button></a>
          <a href="{{ site.details_link }}"><button class="btn"><i class="fa fa-search "></i> Details</button></a>
</div>

# Welcome to PyBugHive website!

<strong>PyBugHive</strong> is a benchmark of <strong>{{ site.bugs }}</strong> <strong>real, manually validated bugs</strong> from <strong>{{ site.projects }}</strong> Python projects.

## Detailed Bugs
Each entry in our database contains the summary of the <strong>bug report</strong>, the <strong>corresponding patch</strong>, and the <strong>test cases</strong> that expose the given bug and the necessary commands to <strong>setup the environment</strong> and <strong>execute the test cases</strong>.

## Rich Interface
<strong>PyBugHive</strong> features a <strong>rich command line interface</strong> for <strong>accessing the buggy and fixed versions</strong> of the programs and <strong>provides the abstraction</strong> for executing the corresponding test cases.
The interface facilitates highly reproducible <strong>empirical research and tool comparisons</strong> in fields such as <strong>testing, automated program repair, or bug prediction</strong>.

### How to cite?

```bib
SOON
```
