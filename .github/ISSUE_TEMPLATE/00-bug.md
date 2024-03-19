name: Bug Report
description: Report a bug and we will do our best to fix it.
title: '[Bug]: '
labels: 'type: Bug'

body:
  - type: markdown
    attributes:
      value: "### Summary of Problem"

  - type: textarea
    id: description
    attributes:
      label: Description
      render: true
      placeholder: |
        What behavior did you observe when encountering this issue?
        What behavior did you expect to observe?
    validations:
      required: true

  - type: dropdown
    id: is-blocker
    attributes:
      label: Is this a blocking issue with no known work-arounds?
      options:
        - 'Yes'
        - 'No'
        - "I don't know"
    validations:
      required: true

  - type: markdown
    attributes:
      value: "### Steps to Reproduce"

  - type: textarea
    id: code
    attributes:
      label: Source code
      render: chapel
      placeholder: |
        // Please provide source code that will reproduce the problem.
        // You can insert your code inline if it's not too long.
        // Otherwise, you can attach it as a file or provide a URL to it.
        // To the extent possible, providing simplified programs demonstrating the
        // problem will be appreciated.
        // You can also replace this section with "Associated Future Test(s)" below.

  - type: input
    id: compile-command
    attributes:
      label: Compile command
      placeholder: |
        e.g. `chpl foo.chpl`

  - type: input
    id: execution-command
    attributes:
      label: Execution command
      placeholder: |
        e.g. `./foo -nl 4`
        If an input file is required, include it as well.

  - type: textarea
    id: future-test
    attributes:
      label: Associated Future Test(s)
      render: true
      placeholder: |
        Are there any tests in Chapel's test system that demonstrate this issue?
        e.g. [`test/path/to/foo.chpl`](
              https://github.com/chapel-lang/chapel/blob/main/test/path/to/foo.chpl
              ) #1234

  - type: markdown
    attributes:
      value: "### Configuration Information"

  - type: textarea
    id: configuration
    attributes:
      label: Configuration
      value: |
        - Output of `chpl --version`:
        - Output of `$CHPL_HOME/util/printchplenv --anonymize`:
        - Back-end compiler and version, e.g. `gcc --version` or `clang --version`:
        - (For Cray systems only) Output of `module list`: