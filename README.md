Defects4J -- version 2.0.0 - With Bug-Induction DB + ver.2 repos
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

The bugs
---------------
Each bug has the following properties:

- Issue filed in the corresponding issue tracker, and issue tracker identifier
  mentioned in the fixing commit message.
- Fixed in a single commit
- Minimized: the Defects4J maintainers manually pruned out
  irrelevant changes in the commit (e.g., refactorings or feature additions).
- Fixed by modifying the source code (as opposed to configuration files,
  documentation, or test files).
- A triggering test exists that failed before the fix and passes after the fix
  -- the test failure is not random or dependent on test execution order.

The (b)uggy and (f)ixed program revisions are labelled with `<id>b` and
`<id>f`, respectively (`<id>` is an integer).

Setting up Defects4J
================

Requirements
----------------
 - Java 1.7
 - Git >= 1.9
 - SVN >= 1.8
 - Perl >= 5.0.10

#### Java version
All bugs have been reproduced and triggering tests verified, using the latest
version of Java 1.7.
Note that using Java 1.8+ might result in unexpected failing tests on a fixed
program version. The next major release of Defects4J will be compatible with
Java 8.

#### Perl dependencies
All required Perl modules are listed in `cpanfile`. On many Unix platforms,
these required Perl modules are installed by default. If this is not the case,
you can use cpan (or a cpan wrapper) to install them. For example, if you have
cpanm installed, you can automatically install all modules by running:
`cpanm --installdeps .`

#### Timezone
Defects4J generates and executes tests in the timezone `America/Los_Angeles`.
If you are using the bugs outside of the Defects4J framework, set the `TZ`
environment variable to `America/Los_Angeles` and export it.

Steps to set up Defects4J
----------------

1. Clone Defects4J:
    - `git clone https://github.com/rjust/defects4j`

2. Initialize Defects4J (download the project repositories and external libraries, which are not included in the git repository for size purposes and to avoid redundancies):
    - `cd defects4j`
    - `./init.sh`

3. Add Defects4J's executables to your PATH:
    - `export PATH=$PATH:"path2defects4j"/framework/bin`

4. Check installation:
    - `defects4j info -p Lang`

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


Mining and contributing additional bugs to Defects4J
================
The bug-mining [README](framework/bug-mining/README.md) details the bug-mining process.
        
Versioning information
----------------------
Defects4J uses a semantic versioning scheme (`major`.`minor`.`patch`):

| Change                                  | `major` | `minor` | `patch` |
|-----------------------------------------|:-------:|:-------:|:-------:|
| Addition/Deletion of bugs               |    X    |         |         |
| New/upgraded internal or external tools |         |    X    |         |
| Fixes and documentation changes         |         |         |    X    |

License
---------
MIT License, see [`license.txt`](https://github.com/rjust/defects4j/blob/master/license.txt) for more information.
