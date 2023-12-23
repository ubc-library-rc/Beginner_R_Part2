---
layout: default
title: Fixing Errors
nav_order: 7
---

### Why do errors happen?

From personal experience, being a TA for an R lab, and my time as the libraries Data Analysis and Visualization GAA, there are a few broad categories of errors:

1.  R does not understand what you are asking it for. This includes:

    -   The packages are not loaded

    -   R can't find the file or variable you are asking for

    -   Typos

    -   R is waiting for commands but not getting them. This include parentheses, quotes, and operations (like a plot) that are not closed.

2.  The data are not formatted properly. For example:

    -   You're working with a data frame when it has to be a matrix

    -   A variable is numeric but it needs to be a factor

    -   There as NA or 0 value sin your data and what you are trying to do can't deal with that.

3.  Your code is in the wrong order or you already ran something that can't be run again on your existing data. This is usually the issue is someone says "this worked before".

4.  Other problems. These are harder to solve and are the more expert-level things. This can include having to use different versions of R or R packages, laying many functions together, only running parts of the data at a time to not crash a system, etc. If you encounter these types of errors, you are usually pretty adavanced in R anyway. I rarely see these type of errors when I am helping others.

We are going to go over the errors listed above with examples now and how to fix them.

### 1. R does not understand what you are asking it for

### 2. The data are not formatted properly 

### 3. Code is in the wrong order

### 
