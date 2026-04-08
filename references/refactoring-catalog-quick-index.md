# Refactoring Catalog Quick Index

Use this quick index to pick a refactoring family by intent, then select the smallest operation that addresses the current smell.

## Ch6: First Set Of Refactorings

Intent: Improve readability, naming, and decomposition with low-risk structural moves.

- Extract Function
- Inline Function
- Extract Variable
- Inline Variable
- Change Function Declaration
- Encapsulate Variable
- Rename Variable
- Introduce Parameter Object
- Combine Functions into Class
- Combine Functions into Transform
- Split Phase

## Ch7: Encapsulation

Intent: Hide representation details and tighten data ownership boundaries.

- Encapsulate Record
- Encapsulate Collection
- Replace Primitive with Object
- Replace Temp with Query
- Extract Class
- Inline Class
- Hide Delegate
- Remove Middle Man
- Substitute Algorithm

## Ch8: Moving Features

Intent: Relocate behavior and data to reduce coupling and improve cohesion.

- Move Function
- Move Field
- Move Statements into Function
- Move Statements to Callers
- Replace Inline Code with Function Call
- Slide Statements
- Split Loop
- Replace Loop with Pipeline
- Remove Dead Code

## Ch9: Organizing Data

Intent: Clarify state and value semantics to reduce incidental complexity.

- Split Variable
- Rename Field
- Replace Derived Variable with Query
- Change Reference to Value
- Change Value to Reference

## Ch10: Simplifying Conditional Logic

Intent: Make branching explicit, composable, and easier to evolve.

- Decompose Conditional
- Consolidate Conditional Expression
- Replace Nested Conditional with Guard Clauses
- Replace Conditional with Polymorphism
- Introduce Special Case
- Introduce Assertion

## Ch11: Refactoring APIs

Intent: Simplify call contracts and separate command/query concerns.

- Separate Query from Modifier
- Parameterize Function
- Remove Flag Argument
- Preserve Whole Object
- Replace Parameter with Query
- Replace Query with Parameter
- Remove Setting Method
- Replace Constructor with Factory Function
- Replace Function with Command
- Replace Command with Function

## Ch12: Dealing with Inheritance

Intent: Reshape hierarchies so shared behavior and specialization stay aligned.

- Pull Up Method
- Pull Up Field
- Pull Up Constructor Body
- Push Down Method
- Push Down Field
- Replace Type Code with Subclasses
- Remove Subclass
- Extract Superclass
- Collapse Hierarchy
- Replace Subclass with Delegate
- Replace Superclass with Delegate

## Heuristic For Choosing Families

- Start in Ch6 or Ch7 for most initial cleanup passes.
- Use Ch8 and Ch9 when ownership and data shape are the root issue.
- Use Ch10 for branching complexity, Ch11 for call-shape/API friction.
- Use Ch12 only when inheritance structure clearly causes confusion or churn.
