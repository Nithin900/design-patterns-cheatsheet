# Java Design Patterns Cheat Sheet

My own notes, written in my words while practising. One card per pattern.

<!--
HOW TO ADD A PATTERN
Copy this block to the end of the file, fill it in, commit. Each "## " heading becomes one card.
A line that starts with a label (Problem:, Parts:, Code:, Use when:, Example:) is shown in bold.

## Pattern name
Category: Creational | Structural | Behavioral
Problem: one line, what pain it solves
Parts:
1. ...
2. ...
Code: `one line showing it in use`
Use when: one line
Example: one real place, ideally SecurePay
-->

## Builder
Category: Creational
Problem: A constructor with many parameters, or many optional ones, is hard to read and easy to get in the wrong order.
Parts:
1. **Main class:** `final` fields + `private` constructor, so the object can't change after it's built.
2. **Static inner `Builder`:** holds the values while you set them.
3. **Setter methods:** each one saves a value and returns `this`, so calls chain: `.title(...).text(...)`.
4. **`build()`:** passes the saved values to the private constructor and returns the finished object.

Code: `Payment p = Payment.builder().id("P1").amount(25).build();`
Use when: an object has many fields, especially optional ones, and should be immutable.
Example: SecurePay `Payment` object.
