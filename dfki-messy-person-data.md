# USE CASE Messy Person Data BY ORGANIZATION DFKI

## Context

When persons are mentioned in texts with their first name, last name and/or middle names, there can be a high variation which of their names are used, how their names are ordered and if their names are abbreviated.
For example, "John Fitzgerald Kennedy",  "John",  "Kennedy, J F" and  "J. Kennedy" are variations that refer to the same person.
If multiple persons are mentioned consecutively in very different ways, especially short texts can be perceived as "messy".
In addition, once ambiguous names occur, associations to persons may not be inferred correctly.

See also related question at stackoverflow: https://stackoverflow.com/questions/61751174/is-there-a-solution-in-rml-for-multiple-complex-entities-in-one-data-element-ce

## Challenges

1. optional (middle) names
2. name variations
3. ambiguities
4. short texts

## Resources

- Website / Data (Generator) / Tool / Evaluator: https://github.com/mschroeder-github/person-index
