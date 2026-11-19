## Purpose

This document provides guidelines for creating flowcharts using Mermaid.

## Format

Before we go through the rules, it would be helpful to see an example:
```mermaid
---
title: Authentication via Username and Password
---
flowchart TD
  Start(["User opens application"]) --> DisplayLogin["Display login page"]
  DisplayLogin --> LoadConfig["Read #quot;AUTH_ENDPOINT#quot; from #quot;config.json#quot;"]
  LoadConfig --> EnterCreds["User enters credentials and taps #quot;Login#quot; button"]
  EnterCreds --> AuthCheck{"Authentication succeeds?"}

  AuthCheck -- "Yes" --> Home["Navigate to home page"]
  AuthCheck -- "No" --> Error["Display error message: #quot;Authentication Failed#quot;"]

  style Home fill: honeydew, stroke: seagreen, color: darkgreen
  style Error fill: mistyrose, stroke: indianred, color: darkred
```

As you can see, you must follow the following rules, at least:
- There is a title.
- Two spaces are used for indentation.
- The typical `End` node at the end is unnecessary.
- Color-code leaf nodes based on their success and failure results, as shown in the example.
- Wrap labels in double quotes.
- Wrap technical names (such as file paths, JSON paths, and environment variable names) and user-facing UI text or messages (such as button labels and error messages) in double quotes using `#quot;`.
