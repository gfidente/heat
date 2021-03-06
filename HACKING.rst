Heat style commandments
=======================

- Step 1: Read the OpenStack style commandments
  http://docs.openstack.org/developer/hacking/
- Step 2: Read on

Heat specific commandments
--------------------------

None so far

Creating unit tests
-------------------
For every new feature, unit tests should be created that both test and
(implicitly) document the usage of said features. If submitting a patch for a
bug that had no unit test, a new passing unit test should be added. If a
submitted bug fix does have a unit test, be sure to add a new one that fails
without the patch and passes with the patch.

For more information on creating unit tests and utilizing the testing
infrastructure in OpenStack Heat, please read heat/tests/testing-overview.txt.


Running tests
-------------
The testing system is based on a combination of tox and testr. The canonical
approach to running tests is to simply run the command `tox`. This will
create virtual environments, populate them with dependencies and run all of
the tests that OpenStack CI systems run. Behind the scenes, tox is running
`testr run --parallel`, but is set up such that you can supply any additional
testr arguments that are needed to tox. For example, you can run:
`tox -- --analyze-isolation` to cause tox to tell testr to add
--analyze-isolation to its argument list.

It is also possible to run the tests inside of a virtual environment
you have created, or it is possible that you have all of the dependencies
installed locally already. In this case, you can interact with the testr
command directly. Running `testr run` will run the entire test suite. `testr
run --parallel` will run it in parallel (this is the default incantation tox
uses.) More information about testr can be found at:
http://wiki.openstack.org/testr


Heat Specific Commandments
--------------------------

- [Heat301] Use LOG.warning() rather than LOG.warn().
- [Heat302] Python 3: do not use dict.iteritems.
- [Heat303] Python 3: do not use dict.iterkeys.
- [Heat304] Python 3: do not use dict.itervalues.

