#   Processing Data with the Shell

Although sophisticated data-processing facilities exist within scripting languages like Ruby or Python, they generally require the inclusion of libraries to access on-disk data and are thus somewhat unwieldy.  Bash may be the preferred option when accessing plain-text data stored across a large number of files.  You have available to you a collection of numbered records enumerating the current list of exoplanets identified by NASA which are stored in a set of separate files.

- [`exoplanets.tar.gz`](repo:./resources/exoplanets.tar.gz)

You should compose two Bash scripts.  The first shell script should be capable of loading a CSV file, determining whether or not the header line(s) need(s) to be preserved, and writing or appending the contents to an aggregate CSV file in record number order (field `NUMBER`).  (Any header lines should be preserved in the first case when the aggregate file is created.  You may assume that the header line(s) is/are the same in all subsequent files.  You may also alter the original data formatting if, for instance, you need to align the fields with tabs or commas better.)  The second shell script should accept a starting record number and an ending record number (inclusive), and return (to stdout) those records.  If the first script is helpful to the task it may be invoked within this second script.

Submit your scripts with the names `collect-netid.sh` and `slice-netid.sh` inside of an archive `netid.tar.gz`, where `netid` should be replaced with your actual NetID.  (Please make sure to use `tar cvzf` to compress; sometimes students submit `zip` or other files that interfere with the grading process.)

A full-credit solution includes:
-   `collect-netid.sh` (50%) which:
    -   loads the CSV files from disk (10%)
    -   preserves or not the header lines as appropriate (30%)
    -   writes out or appends the contents as appropriate (10%)
-   `slice-netid.sh` (50%) which:
    -   accepts a starting and ending record number (10%)
    -   finds and selects out the appropriate records (inclusive) (30%)
    -   returns the records (inclusive) to `stdout` (10%)
