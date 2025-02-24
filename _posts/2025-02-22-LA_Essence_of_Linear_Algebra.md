---
title:  Essence of Linear Algebra
author: jaeman
date: 2025-02-22 19:47:00 +0900
categories: [CSE Undergraduate - Mathematics, Linear Algebra]
tags: [CSE, Mathematics, Linear Algebra]
toc: true
---

## 1. Essence of Linear Algebra
### Vector
list of numbers, point, direction and length.
### Linear combinations
linear combination of two vector $\vec v$ and $\vec w$: (a and b are Scalar) $a\vec v\ +\ b\vec w$
### span
span is the set of all of their linear combinations
### Linearly dependent/independent
if ${\vec v}$ can represented with ${a\vec w}$, ${\vec v}$ and ${\vec w}$ are linearly dependent. ${\vec v}=a\vec w$
which means a linear combinations with linearly dependent vector, it doesn't add any span

Linearly dependent $\vec u$ with $\vec v$ and $\vec w$:
for all values of a and b, $\vec u=a\vec v\ +\ b\vec w$
Linearly independent $\vec u$ with $\vec v$ and $\vec w$:
for all values of a and b, ${\vec u\ \not=\ a\vec v\ +\ b\vec w}$
### basis
the base unit of the coordinate system.
*ex)* we choose to use the \[1,0], \[0,1] as default basis of xy coordinate

*The basis of a vector space is a set of linearly independent vectors that span the full space*
### Linear transformation
#### terms
'Transformation' is same as a function and means it is moved. input->output
'Linear':
1. Lines remain lines
	(all the horizontal, vertical, diagonal lines should not curved, \
	Grid lines remain parallel and evenly spaced)
2. Origin remains fixed
#### method
record the vectors after the basis changes, that is the way that linear transformation affect the vectors.
