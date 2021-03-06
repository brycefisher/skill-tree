# Skill Tree

The "skill tree" package is a tool that you can use to plot out your overall
trajectory. It is meant to be really easily integrated into `mdbook` but also
usable stand-alone.

## Example

Here is an example of what a skill tree looks like. Check out [the source on github][src].

[src]: https://github.com/nikomatsakis/skill-tree/tree/master/src/book/src/skill_tree.md

```skill-tree
[[group]]
name = "legend"
label = "Legend"
header_color = "red"
items = [
  { label = "Unassigned", status = "Unassigned" },
  { label = "Blocked", status = "Blocked" },
  { label = "Assigned / In-progress", status = "Assigned" },
  { label = "Complete", status = "Complete" }
]

[[group]]
name = "align-rustc-predicate"
label = "Align rustc predicates with chalk predicates"
items = [
  { label = "isolate Binder into a Forall goal" },
  { label = "introduce Implication" },
  { label = "introduce Forall goals with types" },
]

[[group]]
name = "recursive-solver"
label = "Experiment with a recursive chalk solver"
items = [
  { label = "write-up the idea that Niko had" },
  { label = "build prototype and evaluate" },
]

[[group]]
name = "rust-analyzer-integration"
label = "Integrate with rust-analyzer"
items = [
  { label = "How to model impl Trait" },
  { label = "Ensure that we never need to ask for impls of unknown types", port = "askfor", requires = ["syntactic-semantic-equality"] },
  { label = "Deal with performance problems" },
  { label = "Deal with memory usage" },
]

[[group]]
name = "syntactic-semantic-equality"
label = "Separate syntactic equality from semantic equality"
requires = ["map-chalk-types-to-rustc-types:debruijn"]
items = [
]

[[group]]
name = "map-chalk-types-to-rustc-types"
label = "Map chalk types to rustc types"
href = "http://example.org"
items = [
  { label = "Move Identifier to TypeFamily" },
  { label = "Adapt rutsc's debruijn index model", port="debruijn" },
  { label = "Remove all vectors, boxes" },
  { label = "Make intern methods take &amp;self" },
]

[[group]]
name = "rustc-integration-mvp"
label = "Integrate chalk-solve into rustc"
requires = [ "map-chalk-types-to-rustc-types" ]
items = [
  { label="remove old chalk support" },
  { label="create" },
]
```
