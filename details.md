---
layout: default
---
<div id="btn_box">
          <a href="{{ site.home_link }}"><button class="btn"><i class="fa fa-home "></i> Home</button></a>
          <a href="{{ site.pdf_link }}"><button class="btn"><i class="fa fa-file"></i> PDF</button></a>
          <a href="{{ site.github_link }}"><button class="btn"><i class="fa fa-github"></i> GitHub</button></a>
          <a href="{{ site.download_link }}"><button class="btn"><i class="fa fa-download"></i> Download </button></a>
          <a href="{{ site.details_link }}"><button class="btn active"><i class="fa fa-search"></i> Details</button></a>
</div>

### Projects

**Name**|**Issues**| **Domain**  |                            **LOC**  |  **Test<br>(LOC)**  | **Stars**|   **Forks**  | **Commits** |   **Years<br>Active** |
|--|--|--|--|--|--|--|--|
[psf/black](https://github.com/psf/black)|                                             38| code formatter |                         303 466  |    12 709    |  33 389   |    2 161      | 1 627         |    5 |
[cookiecutter/cookiecutter](https://github.com/cookiecutter/cookiecutter) |             2| project generator from templates |         5 631  |     4 055    |  20 162   |    1 892      | 3 011         |   10 |
[Rapptz/discord.py](https://github.com/Rapptz/discord.py)|                              2| Discord bot    |                          37 960  |    1 464     |  13 368   |    3 773      | 4 906         |    8 |
[freqtrade/freqtrade](https://github.com/freqtrade/freqtrade)|                         15| cryptocurrency trading|                   73 015  |   41 765     |  22 755   |    5 213      | 22 035        |    6 |
[numpy/numpy](https://github.com/numpy/numpy)|                                         1 | numerical computing   |                  170 179  |   91 891     | 24 344    |  8 459        | 33 396        |   13 |
[pandas-dev/pandas](https://github.com/pandas-dev/pandas)|                             43| data analysis       |                    394 739  |   268 554    |  39 550   |  16 639       | 33 195        |   13 |
[python-poetry/poetry](https://github.com/python-poetry/poetry)|                       11| package manager and builder    |          39 411  |    24 504    |  26 358   |   2 050       | 2 938         |    5 |
[saltstack/salt](https://github.com/saltstack/salt) |                                   7| configuration management/automation|     747 255  |   307 831    | 13 472    |   5 471       | 118 331       |   12 |
[scrapy/scrapy](https://github.com/scrapy/scrapy) |                                     2| web scraping                    |         45 052  |   29 105     |  48 267   |  10 127       | 10 032        |   13 |
[explosion/spaCy](https://github.com/explosion/spaCy) |                                11| Natural language processing |             89 644  |    30 771    |  26 954   |   4 232       | 15 984        |    9 |
[google/jax](https://github.com/google/jax) |                                17| program transformation |             179 079  |    90 476    |  28 316   |   2592      | 20 893        |    6 |
**Average** |                                                                     **13** |                  |                  **189 584**   |  **82 102**  | **26 994**|  **5 691**    |**24 213**     |**10**|

### Using PyBugHive
Using <strong>PyBugHive</strong> is straightforward as all commands (besides the clean command) follow the same pattern: <em>python
pybughive.py {command} {project}-{issue}</em>, where <em>{project}</em>
is the name of the selected project’s repository and <em>{issue}</em> is
the number of the selected issue.
The possible commands are the following:
<ul>
<li><strong>checkout:</strong> Clones the selected repository and checks out
the appropriate commit hash. This should be the first
command when using this tool.</li>
<li><strong>install:</strong> Searches for the appropriate install steps and
runs them. This should be the second command.</li>
<li><strong>test:</strong> Runs the appropriate test steps. When used with the
--all flag, instead of testing just the file(s) included in
the issue, it runs all tests.</li>
<li><strong>fix:</strong> Installs the fix for the selected bug.</li>
<li><strong>clean:</strong> This command does not need a project or an issue
number. It deletes all temporary files generated during
the run. When used with the <em>--all</em> flag, it deletes everything
the tool downloaded, including the repositories.</li>
</ul>
Before <strong>PyBugHive</strong> can be used, it needs to be configured
by setting the <em>INSTALL_DIRECTORY</em>, which specifies where
to download the repositories, and the <em>MONGO_URL</em>, which
specifies the connection string to MongoDB. There are three
ways the user can provide these:
<ol>
<li> Add them to the system’s environment variables.</li>
<li>  Create a .env file in the <strong>PyBugHive</strong>  project root and
   add the above variables to it.</li>
<li>  Same as 2), but with a <em>config.py</em> file.
   We offer a Docker image with everything pre-installed,
   which further helps with an isolated run of <strong>PyBugHive</strong>. Moreover,
   we provide an installer script (setup.sh) that installs all
   required Python versions and other dependencies needed to
   successfully run any bug presented in our database. However,
   for better isolation, we recommend using the Docker environment.</li>
</ol>

### Offline version
A major concern for bug databases is to continuously ensure
the reproducibility of bugs, for example, due to
continuously changing dependencies and improperly locked
dependency versions.
This is the main reason why we created an offline version
of <strong>PyBugHive</strong>. This version of the dataset does not need a
database connection or even an internet connection so the
database can be used in a completely offline environment as
well. For each bug, we downloaded the specific project both
before and after the fix, created the corresponding environment,
and compressed everything into a zip file. This way,
the users do not have to install the particular project manually;
the provided virtual environment is already prepared, and the
tests can be run. The drawback of this version is its large size.