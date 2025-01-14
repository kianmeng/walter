walter
======

Single header library for writing unit tests in C made with fewer
complications by avoiding boilerplate.  Comparing to other similar
libraries this focus on minimizing tests setup and prints direct paths
with line number to failed assertions and tests.

I would like to say that code is simple but it's mostly macro magic
and global state.  So better hold your wizards hat while reading.

Detailed documentation can be found inside library file `walter.h`.
Examples can be found in `demo/` and `demo.t.c`.

	walter.h        Library, includes licence and documentation
	build           Script to builds demo test programs and demo.t.c
	demo/           Demonstration programs
	snap/           Snapshots of expected output in demo.t.c tests

Should work on POSIX systems.
Should NOT work on Windows.


2024.01.06 Sat 20:13	TODO

I just realized that I can easily work with standard input, output and
error when running commands but I can't do that with functions.  Now
I'm in need of such capability.  This has to be thought through and at
the moment I don't have any clear vision.  It might be difficult I'll
come back later.

I also want to provide an flag to enable printing of absolute paths to
test file with failed assertion instead of relative path as it is now.

One more thing.  The basic assertion macros where fine for all my use
cases so far but having just the OK() macro for testing numbers is not
convenient when the assertion fails.  This is because unlike in string
assertions, OK() macro will not print what was the actual value when
it was not what we expected.  There is a way to do generics in C and
by that I could handle all the different numbers with single macro but
I would like to avoid generics.
