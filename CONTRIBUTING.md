# Contributing to Checksum

_Thanks for taking the time to contribute!_

Remember, these guidelines are not considered to be hard and fast rules. So,
always use your best judgment.

## Required stuff

Have a look through the [installation file](INSTALL.md) to gain a good
understanding of what you will need for this project, with regards to software
requirements. Also, read the last section regarding build system features,
because you will probably be using those a lot.

## Expected contributions

Checksum expects the following forms of contribution:

- Bug reports.
- Bug fixes.
- Feature reports.
- Feature implementations.
- Additions or improvements to documentation.
- Additions or improvements to unit tests.
- Additions or improvements to build system.
- Additions or improvements to CI workflow.

## Submitting changes to the code base

1. Make a fork of this project.
1. Clone your fork.
1. Make your changes in that fork on a topic branch.
1. Ensure your code passes the CI workflow.
1. Create a pull request of your changes comparing your topic branch to
   Checksum's `master` branch.
1. Await code review such that you should fix any issues brought up during the
   review.
1. Watch your code get merged, be proud, and repeat the process until you run
   out of coffee and your realize its 3 AM.

## Coding style

> When I wrote it, only God and I knew the meaning; now only God knows.

Yeah... lets try to avoid this kind of situation.

### Conventions

All source code in Checksum's code base must be written using C++17, without any 
extensions.

This project likes to use Mozilla's source code formatting. Do not worry, the
project offers a template configuration file named `.clang-format` that allows
you to use clang-format to automatically format your code.

However, the general rules for formatting are:

- Use 2 spaces for indentation.
- Lines of code must not surpass 80 characters.
- Place opening braces on the same line as control flow statements, while
  function and method names have the opening brace on a new line.
- Use the `m_` prefix for private member variables.
- Use CamelCase for namespaces and classes, camelBack for variables, members,
  function names, and method names, and UPPER\_CASE for macro definitions and
  global variables.
- Try to keep the indentation level of your code below a maximum of 5.

File names should also use CamelCase followed by `.hpp` for header or `.cpp` for
source. Inclusion guards should be named by the file itself, e.g., FooBar.hpp
equates to a `FOO_BAR_HPP` inclusion guard name.

If you have any concerns about the conventions your code uses, then validate
your code using the clang-tidy linter tool. The project comes with a
`.clang-tidy` file that should tell clang-tidy what to check for. All you have
to do is point it towards `compile_commands.json` file, which should be located
in the `build/` directory, e.g., `clang-tidy -p=build/ src/*.cpp`.

### Documentation

You must document your source code using Doxygen comments. Use C style comments
when documenting classes, namespaces, methods, and functions. However, use C++
style comments for variables, and members.

All documentation comments should remain within header files, unless you have
functions and variables with static scope in source files. Also use the `@`
symbol instead of `\` in Doxygen comments, e.g., `@brief` not `\brief`.

State what version your code was implemented in via `@since`. If your code
offers exception guarantees, then state it via `@exception` and state what
it should throw via `@throw`.

Your documentation should explain the _what_ and the _why_, while your code
explains the how. The only exception being that your code has reached a level of
optimization so advanced that further explanation would be warranted.

## Commit style

General commit style rules (obtained from [Chris Beams article][commit-style]):

1. Separate subject from body with a blank line.
1. Limit the subject line to 50 characters.
1. Capitalize the subject line.
1. Do not end the subject line with a period.
1. Use the imperative mood in the subject line.
1. Wrap the body at 72 characters.
1. Use the body to explain _what_ and _why_ vs _how_.

However, you must always signoff your commits in compliance to the [Linux
Developer Certificate of Origin (DCO)][git-dco] as legal way to prove that you
have the right to submit your work. If you do not signoff all of your commits,
then your pull request will be rejected due to the usage of the [DCO
app][dco-app].

[git-dco]: https://developercertificate.org/
[dco-app]: https://github.com/probot/dco
[commit-style]: https://chris.beams.io/posts/git-commit/
