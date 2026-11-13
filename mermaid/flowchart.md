## Purpose

This document provides guidelines for creating flowcharts using Mermaid.

## Format

Before we go through the rules, it would be helpful to see an example:
```mermaid
---
title: Authentication via Username and Password
---
flowchart TD
  Start([User opens application]) --> DisplayLogin[Display login page]
  DisplayLogin --> EnterCreds[User enters username and password and taps Login button]
  EnterCreds --> AuthCheck{Authentication succeeds?}

  AuthCheck -- Yes --> Home[Navigate to home page]
  AuthCheck -- No --> Error[Display error message: Authentication Failed]

  style Home fill: honeydew, stroke:seagreen, color:darkgreen
  style Error fill: mistyrose, stroke:indianred, color:darkred
```

As you can see, you must follow the following rules, at least:
- There is a title.
- Two spaces are used for indentation.
- The typical `End` node at the end is unnecessary.
- Color-code leaf nodes based on their success and failure results, as shown in the example.
