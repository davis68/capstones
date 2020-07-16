# SQL Capstone

## Overview

This capstone project is built around using SQL to clean and modify a data set describing phasor measurement unit (PMU) electrical usage data.

## Target Usage

## Development

Phasor measurement units record electrical supply and usage characteristics at the end user, such as frequency, voltage, and amperage.  You have available in the compressed file `pmu-data.tar.gz` a collection of CSV files which contain readings taken between 1:46 p.m. on April 21, 2014, and 7:20 a.m. on April 22, 2014.  Since the device is sampling ten times a second, there are 632,540 time samples with 30–46 recorded values at each time step.

-    [`pmu-data.tar.gz`](repo:./resources/pmu-data.tar.gz)

You have been asked to clean the data prior to an analysis of the system response to external factors such as weather or propagating grid load changes.  The data are fairly messy however, and may contain invalidating features such as:

-   Missing data, which may show up as an incorrect number of columns.
-   Misaligned data, which may show up as values outside of the expected range or of the wrong type.  For instance, the frequency should always be near 60 Hz, and the voltage near 120 V.  Feel free to suggest or attempt to apply other criteria as appropriate (such as that strings should read `"Good"` instead of other values).

Your solution should check for missing data and for misaligned data.  This will mean establishing the normal limits of the field.  (For instance, the phase cannot go beyond $-180$ to $180$ degrees.)

Bad data should not be corrected, but should simply be removed from the record (*i.e.*, you can remove the entire time step or fill in blanks for the bad data.  Some PMUs recorded data at a different interval from the others, though, and these data are not invalid.  (Examine the files to see what this means.)

Compose a script to process the data.  Your script should load each file, filter out bad data according to the criteria given above, and return a cleaned-up version in a _single_ file (do not repeat the headers).  You may use `sed`, `awk`, `grep`, and `cut`, and your solution should include a loop as well.

Submit your script with the name `pmufix-netid.sh`, where netid should be replaced with your actual NetID.

A full-credit solution includes:
-   `pmufix-netid.sh` (100%) which:
    -   loads the CSV files from disk (10%)
    -   preserves good data (40%)
    -   filters out bad data (40%)
    -   writes out or appends the contents as appropriate (10%)
