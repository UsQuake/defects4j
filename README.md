Defects4J(ver.2 with bug-induction DB + ver.2 repos)
================
Defects4J(ver.2) is a deprecated collection of reproducible bugs and a supporting infrastructure
with the goal of advancing software engineering research enhanced with bug induction informations.

[Find out *InduceBenchmark* of *Ming Wen*!](https://github.com/MingWEN-CS/InduceBenchmark)

Contents of Defects4J
================

The projects
---------------
Defects4J contains 438 bugs from the following open-source projects:

| Identifier | Project name         | Number of bugs |
|------------|----------------------|----------------|
| Chart      | JFreeChart           |  26            |
| Closure    | Closure compiler     | 176            |
| Lang       | Apache commons-lang  |  65            |
| Math       | Apache commons-math  | 106            |
| Mockito    | Mockito              |  38            |
| Time       | Joda-Time            |  27            |

The bug induction information
---------------
[Here!](bug_induce.csv)

Setting up Defects4J
================

Requirements
----------------
 - Java 11
 - Git >= 1.9
 - SVN >= 1.8
 - Perl >= 5.0.10
 - Timezone(export TZ=America/Los_Angeles)
 - Perl dependencies(`cpanm --installdeps .`)

Using Defects4J
================

#### Example commands
1. Get information for a specific project (commons lang):
    - `defects4j info -p Lang`

2. Get information for a specific bug (commons lang, bug 1):
    - `defects4j info -p Lang -b 1`

3. Checkout a buggy source code version (commons lang, bug 1, buggy version):
    - `defects4j checkout -p Lang -v 1b -w /tmp/lang_1_buggy`

4. Change to the working directory, compile sources and tests, and run tests:
    - `cd /tmp/lang_1_buggy`
    - `defects4j compile`
    - `defects4j test`

5. The scripts in [`framework/test/`](tree/master/framework/test/)
are examples of how to use Defects4J, which you might find useful
as inspiration when you are writing your own scripts that use Defects4J.

Command-line interface: defects4j command
-----------------------
Use [`framework/bin/defects4j`](http://people.cs.umass.edu/~rjust/defects4j/html_doc/defects4j.html) to execute any of the following commands:

| Command        | Description                                                                                       |
|----------------|---------------------------------------------------------------------------------------------------|
| [info](http://people.cs.umass.edu/~rjust/defects4j/html_doc/d4j/d4j-info.html)           | View configuration of a specific project or summary of a specific bug                             |
| [checkout](http://people.cs.umass.edu/~rjust/defects4j/html_doc/d4j/d4j-checkout.html)       | Checkout a buggy or a fixed project version                                                       |
| [compile](http://people.cs.umass.edu/~rjust/defects4j/html_doc/d4j/d4j-compile.html)        | Compile sources and developer-written tests of a buggy or a fixed project version                 |
| [test](http://people.cs.umass.edu/~rjust/defects4j/html_doc/d4j/d4j-test.html)           | Run a single test method or a test suite on a buggy or a fixed project version                    |
| [mutation](http://people.cs.umass.edu/~rjust/defects4j/html_doc/d4j/d4j-mutation.html)       | Run mutation analysis on a buggy or a fixed project version                                       |
| [coverage](http://people.cs.umass.edu/~rjust/defects4j/html_doc/d4j/d4j-coverage.html)       | Run code coverage analysis on a buggy or a fixed project version                                  |
| [monitor.test](http://people.cs.umass.edu/~rjust/defects4j/html_doc/d4j/d4j-monitor.test.html)   | Monitor the class loader during the execution of a single test or a test suite                    |
| [export](http://people.cs.umass.edu/~rjust/defects4j/html_doc/d4j/d4j-export.html)         | Export version-specific properties such as classpaths, directories, or lists of tests             |

License
---------
MIT License, see [`license.txt`](https://github.com/rjust/defects4j/blob/master/license.txt) for more information.
