# Unexpected Results with CSS `calc()` and Percentages

This repository demonstrates a subtle bug related to the CSS `calc()` function when used with percentages and dimensions that depend on the element's own size.  The calculation is not performed until *after* the containing block's dimensions are established, which can lead to unexpected sizing inconsistencies.

## The Bug

The provided `bug.css` file shows a simple example where a div's height is calculated as 100% of the parent's height minus 10px using `calc()`.  This works fine if the parent's height is already known. However, if the parent's height depends on its content (including the div's height), the calculation can be incorrect.

## The Solution

`bugSolution.css` provides a solution to work around this behavior. In this case, using javascript to fix this issue may be better than using solely CSS.  It's crucial to carefully consider the dependencies in your layouts when using `calc()` with percentages.