metac++
========

You can write C++ while you write C++.

# Abstract

You can write code in a subset of C++, in C++ using a special DSL (Domain Specific Language).

# Table of contents

1. Expressions
2. Laziness
3. Context of evaluation
4. New keywords

## Expressions

Everything is an expression.

## Laziness

Every expression is lazy. If you evaluate an expression, every child expression is evaluated recursively.

	var fn = fun<3>

## Context of evaluation

If you evaluate function expression all the expressions evaluated recursively are using this single context of evaluation.

## New keywords

These keywords are not really keywords like `for`, `if` because we are limited to the C++ standard which does not allow such things. For each duplicated keywords there is `_` appended to the word.

 * `if` becomes `if_`.
 * `else` becomes `else_`.
 * `try_` becomes `try_`.

etc.

### var

All expressions could be stored in a `var` objects. `var` objects are lazy.

### eval

Forces evaluation of a lazy expression.

	var expr = fib(42);
	var number = (eval)expr;
	int result = (eval)number;

Here `number` is a lazy integer. But `result` is a standard `int` value with the `fib` result.

### fun

Usage: `fun<arity>`

 * `arity` is a number of parameters used.

To define function you have to call it this way:

	var fn = fun<0>()[
		print("Hello world!")
	];

You can call `fn` later using forced evaluation:

	(eval)fn;

# Compatibility

`metacpp` aims to be C++03 compatible. Current implementation uses few C++11 constructs.

# License

The project is developed in the open and license will be announced soon.

# Author

Michał Papierski