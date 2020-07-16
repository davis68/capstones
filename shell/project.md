# Shell Capstone

## Overview

This capstone project is built around using the command line (Bash or close equivalent) to process a data collection consisting of many files.

## Target Usage

```bash
$ collect.sh fileheader
$ extract.sh 28
```

## Development

Although sophisticated data-processing facilities exist within scripting languages like Ruby or Python, they generally require the inclusion of libraries to access on-disk data and are thus somewhat unwieldy.  Bash may be the preferred option when accessing plain-text data stored across a large number of files.  You have available to you a collection of numbered records enumerating the current list of exoplanets identified by NASA which are stored in a set of separate files.

- [`exoplanets.tar.gz`](repo:./resources/exoplanets.tar.gz)

You may need to learn a bit more about the shell in order to process certain kinds of data.  For instance, how can you make a decision whether or not a particular line is a header line, and thus should be skipped?

You should compose two Bash scripts, `collect.sh` and `extract.sh`.

### `collect.sh`

The first shell script should be capable of loading a CSV file, determining whether or not the header line(s) need(s) to be preserved, and writing or appending the contents to an aggregate CSV file in record number order (field `NUMBER`).  (Any header lines should be preserved in the first case when the aggregate file is created.  You may assume that the header line(s) is/are the same in all subsequent files.  You may also alter the original data formatting if, for instance, you need to align the fields with tabs or commas better.)

### `extract.sh`

The second shell script should accept a starting record number and an ending record number (inclusive), and return (to `stdout`) those records.  If the first script is helpful to the task it may be invoked within this second script.

## Progress & Completion

You should fork this project and work exclusively in the `shell/` folder.  We expect you to compose two scripts:

- `collect.sh` as described above.
- `extract.sh` as described above.
