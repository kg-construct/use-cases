# USE CASE Messy Spreadsheets BY ORGANIZATION DFKI

## Context

When spreadsheets are filled freely by knowledge workers, they can contain rather unstructured content.
For humans and especially machines it becomes difficult to interpret such data properly.
If a data maintenance strategy has been missing and user-generated data becomes "messy", the construction of knowledge graphs will be a challenging task.

## Challenges

1. Multiple Surface Forms: Entities can be mentioned in various ways.
2. Mixed Date Representations: Dates can be represented in various formats.
3. Acronyms and Symbols: To reduce typing effort, users tend to write acronyms or even single symbols.
4. Free Comments: In spreadsheets, users are able to edit cells in order to write small comments.
5. Style Usage: Changing style is a common way to express additional information in cells (e.g. struck out).
6. Multiple Entities in a Cell: If a table is unnormalized, data redundancies can occur. Cell contents have to be split appropriately.
7. Multiple Types in a Table: dynamically assigning types to extracted row entities.
8. Implicit Relationship: Users tend to write identical texts (like IDs) in different cells to express an implicit relationship.

Based on observations in a work (currently under review) mapping approaches seems to struggle with:
(5.) Style Usage, (6.) Multiple Entities in a Cell and (8.) Implicit Relationship.

See also for (6.) a related question at stackoverflow: https://stackoverflow.com/questions/61751174/is-there-a-solution-in-rml-for-multiple-complex-entities-in-one-data-element-ce

## Resources

Dataset is privat, because it is from an industrial scenario.
Paper with proposed approach is currently under review.
