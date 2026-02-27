# USE CASE XXXX BY ORGANIZATION/GROUP YYY

## Context

Brought to my (Maxime Lefrançois) attention by an engineer in an energy company

## Challenges

From the following document (hierarchy of codes): 

```
.root
.child1
..child11
..child12
.child2
..child21
```

We would want to generate the skos concept hierarchy: 

```
<root> skos:narrower <child1> .
<child1> skos:narrower <child11> .
<child1> skos:narrower <child12> .
<root> skos:narrower <child2> .
<child2> skos:narrower <child21> .
```


