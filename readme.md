
# Semantic Rule Engines Comparison (Additional materials)

Inference engines (reasoners) considered by this study include the following:

1. Pellet2 (SWRL) \(also provides a plugin for Protege) is the only OWL reasoner supporting SWRL built-ins (arithmetics, etc.).
2.  Apache Jena - RDF/OWL framework for Java having custom production rule syntax.
3.  SWI-Prolog[10] with the semweb (rdf11) package for handling RDF data alongside prolog native predicates representing the domain rules.
4.  Apache Jena ARQ - a `SPARQL` query processor capable running batches of SPARQL Update queries imitating production rules.
5.  Closed World Machine [seems impractical as not supported since 2008] - ancient reasoner written in Python 2 for RDF with its own rule syntax supporting some useful built-ins.
6. Clingo - Answer Set Programming (ASP) tool that combines `gringo` grounder and `clasp` solver \(handles data as ASP facts, no native support for RDF).
7. DLV [seems impractical as not supported since 2012] - another  ASP  solver  using  a  dialect  of  ASP  slightly  different  from Clingo’s one.


|        Feature        |    SWRL    | Jena Rules | SWI-Prolog + rdf11 |  SPARQL Update  | ASP (Clingo) |
|:---------------------:|:----------:|:----------:|:------------------:|:---------------:|:------------:|
| Open/Closed World     | OWA        | CWA        | CWA                | CWA             | CWA          |
| Arithmetic built-ins  | Yes        | Yes        | Yes                | Yes             | Yes          |
| Assert relations      | Yes        | Yes        | Yes                | Yes             | Yes          |
| Retract relations     | No         | Yes        | Yes                | Yes             | No           |
| Create individuals    | No         | Yes        | Yes                | Yes             | Yes          |
| Create classes        | No         | Yes        | Yes                | Yes             | Yes          |
| Data structures       | Plain      | Plain      | Nested             | Plain           | Nested       |
| Rule composition      | No         | No         | Yes                | Nested  SELECTs | No           |
| Negation support      | No         | Yes        | Yes                | Yes             | Yes          |
| Aggregates            | No         | No         | User-defined       | Built-in        | Built-in     |
| Integrity constraints | No         | No         | No                 | No              | Yes          |
| Check transitivity    | Assert all | Assert all | Recursion          | Property path   | Assert all   |
| Custom builtins       | Yes – Java | Yes – Java | Yes – Prolog       | No              | Yes – Lua    |
| Prioritize rules      | No         | No         | Ordering only      | Ordering only   | No           |



## Performance Evaluation Results


