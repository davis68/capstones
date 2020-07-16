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


        #   Processing Dirty Data with the Shell

        Phasor measurement units record electrical supply and usage characteristics at the end user, such as frequency, voltage, and amperage.  You have available in the compressed file `pmu-data.tar.gz` a collection of CSV files which contain readings taken between 1:46 p.m. on April 21, 2014, and 7:20 a.m. on April 22, 2014.  Since the device is sampling ten times a second, there are 632,540 time samples with 30–46 recorded values at each time step.

        -    [`pmu-data.tar.gz`](repo:./resources/pmu-data.tar.gz)

        You have been asked to clean the data prior to an analysis of the system response to external factors such as weather or propagating grid load changes.  The data are fairly messy however, and may contain invalidating features such as:

        -   Missing data, which may show up as an incorrect number of columns.
        -   Misaligned data, which may show up as values outside of the expected range or of the wrong type.  For instance, the frequency should always be near 60 Hz, and the voltage near 120 V.  Feel free to suggest or attempt to apply other criteria as appropriate (such as that strings should read `"Good"` instead of other values).

        Your solution should check for missing data and for misaligned data.  This will mean establishing the normal limits of the field.  (For instance, the phase cannot go beyond $-180$ to $180$ degrees.)

        Bad data should not be corrected, but should simply be removed from the record (*i.e.*, you can remove the entire time step or fill in blanks for the bad data.  Some PMUs recorded data at a different interval from the others, though, and these data are not invalid.  (Examine the files to see what this means.)

        Compose a script to process the data.  Your script should load each file, filter out bad data according to the criteria given above, and return a cleaned-up version in a _single_ file (do not repeat the headers).  You may use `sed`, `awk`, `grep`, and `cut`, and your solution should include a loop as well.

        Submit your script with the name `pmufix-netid.sh`, where netid should be replaced with your actual NetID.

    rubric: |
        A full-credit solution includes:
        -   `pmufix-netid.sh` (100%) which:
            -   loads the CSV files from disk (10%)
            -   preserves good data (40%)
            -   filters out bad data (40%)
            -   writes out or appends the contents as appropriate (10%)
