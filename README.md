# Tcl Floating-Point Comparison Bug

This repository demonstrates a subtle bug in Tcl related to comparing floating-point numbers using the `==` operator.  The `==` operator in Tcl performs string comparison, which can lead to incorrect results when comparing floating-point numbers due to their internal representation.

## Bug Description
The provided `bug.tcl` file contains a procedure `badproc` that compares two numbers using the `==` operator.  The expectation is that comparing `1.0` and `1` should return `true`, but the Tcl interpreter interprets these as strings and evaluates to false, leading to an unexpected return value.  This can create issues in conditions and lead to unwanted program behavior. 

## Solution
The `bugSolution.tcl` file shows a corrected version using the `expr` command to perform a numerical comparison.  This ensures that the comparison is performed using the numerical values of the variables rather than their string representations.