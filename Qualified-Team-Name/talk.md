# Qualified Name for Classes and Functions

 Qualifed Team Name
 Hunter Haskins, Jose Escobar, Michael Crozier, Steven Funk

# Python's Scoping Issues

* Python's introspection facilities have long had poor support for nested classes due to only having 3 defined namespaces:
	* Local
	* Global
	*Built-in

```python
def blah():
	"""The blah function demonstrates doc strings"""
	return 42
```	

# Python's Scoping Issues-continued

* The following slides provide a brief history of how a solution is formed
	* Initial attempt at a solution: PEP 227 - Statically Nested Scopes
	* Second attempt: PEP 3104 - Access to Names in Outer Scopes
	* Latest attempt: PEP 3155 - Qualifed Name for Classes and Functions

# PEP 227 - Statically Nested Scopes
* The addition of nested scopes allows resolution of unbound local names in enclosing function's namespaces

* According to Python 2.0: for a function foo defined within a function bar, the names bound in bar are not visible in foo

# PEP 227 - Statically Nested Scopes - continued

* The propoal PEP 227 then changes the rules so that names bound in bar are visible in foo, unless foo conatins a name binding that hides the binding in B

# PEP 227 Specifications
* Changes made by PEP 227 address two problems:
	1. The limited utility of lambda expressions & nested expressions in general
	2. The inability to define reursive functions except at a modular level
* New Feature: Names are introduced by the name binding operations:
	* Operations include: argument declarations, assignments, class and functions definitinos, for statements, and except clauses

# PEP 227 Specifications - continued
