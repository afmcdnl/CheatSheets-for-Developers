# Python CheatSheet for Developers

## Table of Contents

- [1. Collections](#1-collections)
  - [1.1. List](#list)
  - [1.2. Dictionary](#dictionary)
  - [1.3. Set](#set)
  - [1.4. Tuple](#tuple)
  - [1.5. Range](#range)
  - [1.6. Enumerate](#enumerate)
  - [1.7. Iterator](#iterator)
  - [1.8. Generator](#generator)
- [2. Types](#2-types)
  - [2.1. Type](#type)
  - [2.2. String](#string)
  - [2.3. Regular_Exp](#regular_exp)
  - [2.4. Format](#format)
  - [2.5. Numbers](#numbers)
  - [2.6. Combinatorics](#combinatorics)
  - [2.7. Datetime](#datetime)
- [3. Syntax](#3-syntax)
  - [3.1. Args](#args)
  - [3.2. Inline](#inline)
  - [3.3. Import](#import)
  - [3.4. Decorator](#decorator)
  - [3.5. Class](#class)
  - [3.6. Duck_Types](#duck_types)
  - [3.7. Enum](#enum)
  - [3.8. Exception](#sqlite)
  - [3.9. File](#file)
  - [3.10 Bytes](#bytes)
  - [3.11. Struct](#struct)
  - [3.12. Array](#array)
  - [3.13. Memory_View](#memory_view)
  - [3.14. Deque](#deque)
- [4. Functions](#4-functions)
  - [4.1. Lambda](#lambda)
  - [4.2. Map](#map)
  - [4.3. Filter](#filter)
  - [4.4. Reduce](#reduce)
  - [4.5. Zip](#zip)
  - [4.6. Partial](#partial)
  - [4.7. Compose](#compose)
  - [4.8. Currying](#currying)
  - [4.9. Memoize](#memoize)
  - [4.10. Decorator](#decorator)
  - [4.11. Closure](#closure)
  - [4.12. Generator](#generator)
  - [4.13. Iterator](#iterator)
  - [4.14. Context_Manager](#context_manager)
  - [4.15. Decorator](#decorator)
- [5. Modules](#5-modules)
  - [5.1. Argparse](#argparse)
  - [5.2. Logging](#logging)
  - [5.3. Sqlite](#sqlite)
  - [5.4. Pickle](#pickle)
  - [5.5 Collections](#collections)
  - [5.6 Counter](#counter)
  - [5.7 OrderedDict](#ordereddict)
  - [5.8 Defaultdict](#defaultdict)
  - [5.9 Namedtuple](#namedtuple)
  - [5.10 ChainMap](#chainmap)
  - [5.11 Heapq](#heapq)
  - [5.12 Bisect](#bisect)
  - [5.13 Array](#array)
  - [5.14 Weakref](#weakref)
  - [5.15 Types](#types)
  - [5.16 Copy](#copy)
  - [5.17 Pprint](#pprint)
  - [5.18 Reprlib](#reprlib)
  - [5.19 Enum](#enum)
  - [5.20 Pathlib](#pathlib)
  - [5.21 Functools](#functools)
  - [5.22 Itertools](#itertools)
  - [5.23 Contextlib](#contextlib)
  - [5.24 Atexit](#atexit)
  - [5.25 Traceback](#traceback)
  - [5.26 Sys](#sys)
  - [5.27 Io](#io)
  - [5.28 Time](#time)
  - [5.29 Datetime](#datetime)
  - [5.30 Calendar](#calendar)
  - [5.31 Random](#random)
  - [5.32 Statistics](#statistics)
  - [5.33 Math](#math)
  - [5.34 Cmath](#cmath)
- [6. Advanced](#6-advanced)
  - [6.1. Threading](#threading)
  - [6.2. Operator](#operator)
  - [6.3. Introspection](#introspection)
  - [6.4. Metaprogramming](#metaprogramming)
  - [6.5. Eval](#eval)
  - [6.6. Coroutines](#coroutines)
- [7. Libraries](#7-libraries)
  - [7.1. Progress_Bar](#progress_bar)
  - [7.2. Plot](#plot)
  - [7.3. Table](#table)
  - [7.4. Curses](#curses)
  - [7.5. Logging](#logging)
  - [7.6. Scraping](#scraping)
  - [7.7. Web](#web)
  - [7.8. Profiling](#profiling)
  - [7.9. NumPy](#numpy)
  - [7.10. Image](#image)
  - [7.11. Audio](#audio)
  - [7.12. PyGame](#pygame)
  - [7.13. Pandas](#pandas)
  - [7.14 Matplotlib](#matplotlib)

## Main

```python
if __name__ == '__main__':     # Runs main() if file wasn't imported.
    main()
```

**[🔼Back to Top](#table-of-contents)**

## List

```python
<list> = <list>[<slice>]       # Or: <list>[from_inclusive : to_exclusive : ±step]
```

```python
<list>.append(<el>)            # Or: <list> += [<el>] | adds a new element to the end of the list
<list>.extend(<collection>)    # Or: <list> += <collection> | adds all elements of a collection(list,tuples,etc) to the end of the list
```

```python
<list>.sort()                  # Sorts in ascending order.
<list>.reverse()               # Reverses the list in-place.
<list> = sorted(<collection>)  # Returns a new sorted list.
<iter> = reversed(<list>)      # Returns reversed iterator.
```

```python
sum_of_elements  = sum(<collection>)
elementwise_sum  = [sum(pair) for pair in zip(list_a, list_b)]
sorted_by_second = sorted(<collection>, key=lambda el: el[1])
sorted_by_both   = sorted(<collection>, key=lambda el: (el[1], el[0]))
flatter_list     = list(itertools.chain.from_iterable(<list>))
product_of_elems = functools.reduce(lambda out, el: out * el, <collection>)
list_of_chars    = list(<str>)
```

- **For details about sorted(), min() and max() see [sortable](#sortable).**
- **Module [operator](#operator) provides functions itemgetter() and mul() that offer the same functionality as [lambda](#lambda) expressions above.**

```python
<list>.insert(<int>, <el>)     # Inserts item at index and moves the rest to the right.
<el>  = <list>.pop([<int>])    # Removes and returns item at index or from the end.
<int> = <list>.count(<el>)     # Returns number of occurrences. Also works on strings.
<int> = <list>.index(<el>)     # Returns index of the first occurrence or raises ValueError.
<list>.remove(<el>)            # Removes first occurrence of the item or raises ValueError.
<list>.clear()                 # Removes all items. Also works on dictionary and set.
```

**[🔼Back to Top](#table-of-contents)**

## Dictionary

```python
<view> = <dict>.keys()                          # Coll. of keys that reflects changes.
<view> = <dict>.values()                        # Coll. of values that reflects changes.
<view> = <dict>.items()                         # Coll. of key-value tuples that reflects chgs.
```

```python
value  = <dict>.get(key, default=None)          # Returns default if key is missing.
value  = <dict>.setdefault(key, default=None)   # Returns and writes default if key is missing.
<dict> = collections.defaultdict(<type>)        # Returns a dict with default value of type.
<dict> = collections.defaultdict(lambda: 1)     # Returns a dict with default value 1.
```

```python
<dict> = dict(<collection>)                     # Creates a dict from coll. of key-value pairs.
<dict> = dict(zip(keys, values))                # Creates a dict from two collections.
<dict> = dict.fromkeys(keys [, value])          # Creates a dict from collection of keys.
```

```python
<dict>.update(<dict>)                           # Adds items. Replaces ones with matching keys.
value = <dict>.pop(key)                         # Removes item or raises KeyError.
{k for k, v in <dict>.items() if v == value}    # Returns set of keys that point to the value.
{k: v for k, v in <dict>.items() if k in keys}  # Returns a dictionary, filtered by keys.
```

### Counter

```python
>>> from collections import Counter
>>> colors = ['blue', 'blue', 'blue', 'red', 'red']
>>> counter = Counter(colors)
>>> counter['yellow'] += 1
Counter({'blue': 3, 'red': 2, 'yellow': 1})
>>> counter.most_common()[0]
('blue', 3)
```

**[🔼Back to Top](#table-of-contents)**

## Set

```python
<set> = set()                                   # `{}` returns a dictionary.
```

```python
<set>.add(<el>)                                 # Or: <set> |= {<el>}
<set>.update(<collection> [, ...])              # Or: <set> |= <set>
```

```python
<set>  = <set>.union(<coll.>)                   # Or: <set> | <set>
<set>  = <set>.intersection(<coll.>)            # Or: <set> & <set>
<set>  = <set>.difference(<coll.>)              # Or: <set> - <set>
<set>  = <set>.symmetric_difference(<coll.>)    # Or: <set> ^ <set>
<bool> = <set>.issubset(<coll.>)                # Or: <set> <= <set>
<bool> = <set>.issuperset(<coll.>)              # Or: <set> >= <set>
```

```python
<el> = <set>.pop()                              # Raises KeyError if empty.
<set>.remove(<el>)                              # Raises KeyError if missing.
<set>.discard(<el>)                             # Doesn't raise an error.
```

### Frozen Set

- **Is immutable and hashable.**
- **That means it can be used as a key in a dictionary or as an element in a set.**

```python
<frozenset> = frozenset(<collection>)
```

**[🔼Back to Top](#table-of-contents)**

## Tuple

**Tuple is an immutable and hashable list.**

```python
<tuple> = ()                                # Empty tuple.
<tuple> = (<el>,)                           # Or: <el>,
<tuple> = (<el_1>, <el_2> [, ...])          # Or: <el_1>, <el_2> [, ...]
```

### Named Tuple

**Tuple's subclass with named elements.**

```python
>>> from collections import namedtuple
>>> Point = namedtuple('Point', 'x y')
>>> p = Point(1, y=2)
Point(x=1, y=2)
>>> p[0]
1
>>> p.x
1
>>> getattr(p, 'y')
2
```

**[🔼Back to Top](#table-of-contents)**

## Range

**Immutable and hashable sequence of integers.**

```python
<range> = range(stop)                       # range(to_exclusive)
<range> = range(start, stop)                # range(from_inclusive, to_exclusive)
<range> = range(start, stop, ±step)         # range(from_inclusive, to_exclusive, ±step_size)
```

```python
>>> [i for i in range(3)]
[0, 1, 2]
```

**[🔼Back to Top](#table-of-contents)**

## Enumerate

```python
for i, el in enumerate(<collection> [, i_start]):
    ...
```

**[🔼Back to Top](#table-of-contents)**

## Iterator

```python
<iter> = iter(<collection>)                 # `iter(<iter>)` returns unmodified iterator.
<iter> = iter(<function>, to_exclusive)     # A sequence of return values until 'to_exclusive'.
<el>   = next(<iter> [, default])           # Raises StopIteration or returns 'default' on end.
<list> = list(<iter>)                       # Returns a list of iterator's remaining elements.
```

### Itertools

```python
import itertools as it
```

```python
<iter> = it.count(start=0, step=1)          # Returns updated value endlessly. Accepts floats.
<iter> = it.repeat(<el> [, times])          # Returns element endlessly or 'times' times.
<iter> = it.cycle(<collection>)             # Repeats the sequence endlessly.
```

```python
<iter> = it.chain(<coll>, <coll> [, ...])   # Empties collections in order (figuratively).
<iter> = it.chain.from_iterable(<coll>)     # Empties collections inside a collection in order.
```

```python
<iter> = it.islice(<coll>, to_exclusive)    # Only returns first 'to_exclusive' elements.
<iter> = it.islice(<coll>, from_inc, …)     # `to_exclusive, +step_size`. Indices can be None.
```

**[🔼Back to Top](#table-of-contents)**

## Generator

- **Any function that contains a yield statement returns a generator.**
- **Generators and iterators are interchangeable.**

```python
def count(start, step):
    while True:
        yield start
        start += step
```

```python
>>> counter = count(10, 2)
>>> next(counter), next(counter), next(counter)
(10, 12, 14)
```

**[🔼Back to Top](#table-of-contents)**

## Type

- **Everything is an object.**
- **Every object has a type.**
- **Type and class are synonymous.**

```python
<type> = type(<el>)                          # Or: <el>.__class__
<bool> = isinstance(<el>, <type>)            # Or: issubclass(type(<el>), <type>)
```

```python
>>> type('a'), 'a'.__class__, str
(<class 'str'>, <class 'str'>, <class 'str'>)
```

#### Some types do not have built-in names, so they must be imported:

```python
from types import FunctionType, MethodType, LambdaType, GeneratorType, ModuleType
```

### Abstract Base Classes

**Each abstract base class specifies a set of virtual subclasses. These classes are then recognized by isinstance() and issubclass() as subclasses of the ABC, although they are really not. ABC can also manually decide whether or not a specific class is its virtual subclass, usually based on which methods the class has implemented. For instance, Iterable ABC looks for method iter(), while Collection ABC looks for iter(), contains() and len().**

```python
>>> from collections.abc import Iterable, Collection, Sequence
>>> isinstance([1, 2, 3], Iterable)
True
```

```text
+------------------+------------+------------+------------+
|                  |  Iterable  | Collection |  Sequence  |
+------------------+------------+------------+------------+
| list, range, str |    yes     |    yes     |    yes     |
| dict, set        |    yes     |    yes     |            |
| iter             |    yes     |            |            |
+------------------+------------+------------+------------+
```

```python
>>> from numbers import Number, Complex, Real, Rational, Integral
>>> isinstance(123, Number)
True
```

```text
+--------------------+----------+----------+----------+----------+----------+
|                    |  Number  |  Complex |   Real   | Rational | Integral |
+--------------------+----------+----------+----------+----------+----------+
| int                |   yes    |   yes    |   yes    |   yes    |   yes    |
| fractions.Fraction |   yes    |   yes    |   yes    |   yes    |          |
| float              |   yes    |   yes    |   yes    |          |          |
| complex            |   yes    |   yes    |          |          |          |
| decimal.Decimal    |   yes    |          |          |          |          |
+--------------------+----------+----------+----------+----------+----------+
```

**[🔼Back to Top](#table-of-contents)**

## String

```python
<str>  = <str>.strip()                       # Strips all whitespace characters from both ends.
<str>  = <str>.strip('<chars>')              # Strips all passed characters from both ends.
```

```python
<list> = <str>.split()                       # Splits on one or more whitespace characters.
<list> = <str>.split(sep=None, maxsplit=-1)  # Splits on 'sep' str at most 'maxsplit' times.
<list> = <str>.splitlines(keepends=False)    # On [\n\r\f\v\x1c-\x1e\x85\u2028\u2029] and \r\n.
<str>  = <str>.join(<coll_of_strings>)       # Joins elements using string as a separator.
```

```python
<bool> = <sub_str> in <str>                  # Checks if string contains a substring.
<bool> = <str>.startswith(<sub_str>)         # Pass tuple of strings for multiple options.
<bool> = <str>.endswith(<sub_str>)           # Pass tuple of strings for multiple options.
<int>  = <str>.find(<sub_str>)               # Returns start index of the first match or -1.
<int>  = <str>.index(<sub_str>)              # Same, but raises ValueError if missing.
```

```python
<str>  = <str>.replace(old, new [, count])   # Replaces 'old' with 'new' at most 'count' times.
<str>  = <str>.translate(<table>)            # Use `str.maketrans(<dict>)` to generate table.
```

```python
<str>  = chr(<int>)                          # Converts int to Unicode character.
<int>  = ord(<str>)                          # Converts Unicode character to int.
```

- **Also: `'lstrip()'`, `'rstrip()'` and `'rsplit()'`.**
- **Also: `'lower()'`, `'upper()'`, `'capitalize()'` and `'title()'`.**

### Property Methods

```text
+---------------+----------+----------+----------+----------+----------+
|               | [ !#$%…] | [a-zA-Z] |  [¼½¾]   |  [²³¹]   |  [0-9]   |
+---------------+----------+----------+----------+----------+----------+
| isprintable() |   yes    |   yes    |   yes    |   yes    |   yes    |
| isalnum()     |          |   yes    |   yes    |   yes    |   yes    |
| isnumeric()   |          |          |   yes    |   yes    |   yes    |
| isdigit()     |          |          |          |   yes    |   yes    |
| isdecimal()   |          |          |          |          |   yes    |
+---------------+----------+----------+----------+----------+----------+
```

- **Also: `'isspace()'` checks for `'[ \t\n\r\f\v\x1c-\x1f\x85\u2000…]'`.**

**[🔼Back to Top](#table-of-contents)**

## Regex

```python
import re
<str>   = re.sub(<regex>, new, text, count=0)  # Substitutes all occurrences with 'new'.
<list>  = re.findall(<regex>, text)            # Returns all occurrences as strings.
<list>  = re.split(<regex>, text, maxsplit=0)  # Use brackets in regex to include the matches.
<Match> = re.search(<regex>, text)             # Searches for first occurrence of the pattern.
<Match> = re.match(<regex>, text)              # Searches only at the beginning of the text.
<iter>  = re.finditer(<regex>, text)           # Returns all occurrences as Match objects.
```

- **Argument 'new' can be a function that accepts a Match object and returns a string.**
- **Search() and match() return None if they can't find a match.**
- **Argument `'flags=re.IGNORECASE'` can be used with all functions.**
- **Argument `'flags=re.MULTILINE'` makes `'^'` and `'$'` match the start/end of each line.**
- **Argument `'flags=re.DOTALL'` makes dot also accept the `'\n'`.**
- **Use `r'\1'` or `'\\1'` for backreference (`'\1'` returns a character with octal code 1).**
- **Add `'?'` after `'*'` and `'+'` to make them non-greedy.**

### Match Object

```python
<str>   = <Match>.group()                      # Returns the whole match. Also group(0).
<str>   = <Match>.group(1)                     # Returns part in the first bracket.
<tuple> = <Match>.groups()                     # Returns all bracketed parts.
<int>   = <Match>.start()                      # Returns start index of the match.
<int>   = <Match>.end()                        # Returns exclusive end index of the match.
```

### Special Sequences

```python
'\d' == '[0-9]'                                # Matches decimal characters.
'\w' == '[a-zA-Z0-9_]'                         # Matches alphanumerics and underscore.
'\s' == '[ \t\n\r\f\v]'                        # Matches whitespaces.
```

- **By default, decimal characters, alphanumerics and whitespaces from all alphabets are matched unless `'flags=re.ASCII'` argument is used.**
- **As shown above, it restricts all special sequence matches to the first 128 characters and prevents `'\s'` from accepting `'[\x1c-\x1f]'` (the so-called separator characters).**
- **Use a capital letter for negation (all non-ASCII characters will be matched when used in combination with ASCII flag).**

**[🔼Back to Top](#table-of-contents)**

## Format

```python
<str> = f'{<el_1>}, {<el_2>}'            # Curly brackets can also contain expressions. This is named "Fstring"
<str> = '{}, {}'.format(<el_1>, <el_2>)  # Or: '{0}, {a}'.format(<el_1>, a=<el_2>)
<str> = '%s, %s' % (<el_1>, <el_2>)      # Redundant and inferior C style formatting.
```

### Attributes

```python
>>> Person = collections.namedtuple('Person', 'name height')
>>> person = Person('Jean-Luc', 187)
>>> f'{person.height}'
'187'
>>> '{p.height}'.format(p=person)
'187'
```

### General Options

```python
{<el>:<10}                               # '<el>      '
{<el>:^10}                               # '   <el>   '
{<el>:>10}                               # '      <el>'
{<el>:.<10}                              # '<el>......'
{<el>:0}                                 # '<el>'
```

- **Options can be generated dynamically: `f'{<el>:{<str/int>}[…]}'`.**
- **Adding `'!r'` before the colon converts object to string by calling its [repr()](#class) method.**

### Strings

```python
{'abcde':10}                             # 'abcde     '
{'abcde':10.3}                           # 'abc       '
{'abcde':.3}                             # 'abc'
{'abcde'!r:10}                           # "'abcde'   "
```

### Numbers

```python
{123456:10}                              # '    123456'
{123456:10,}                             # '   123,456'
{123456:10_}                             # '   123_456'
{123456:+10}                             # '   +123456'
{123456:=+10}                            # '+   123456'
{123456: }                               # ' 123456'
{-123456: }                              # '-123456'
```

### Floats

```python
{1.23456:10.3}                           # '      1.23'
{1.23456:10.3f}                          # '     1.235'
{1.23456:10.3e}                          # ' 1.235e+00'
{1.23456:10.3%}                          # '  123.456%'
```

#### Comparison of presentation types:

```text
+--------------+----------------+----------------+----------------+----------------+
|              |    {<float>}   |   {<float>:f}  |   {<float>:e}  |   {<float>:%}  |
+--------------+----------------+----------------+----------------+----------------+
|  0.000056789 |   '5.6789e-05' |    '0.000057'  | '5.678900e-05' |    '0.005679%' |
|  0.00056789  |   '0.00056789' |    '0.000568'  | '5.678900e-04' |    '0.056789%' |
|  0.0056789   |   '0.0056789'  |    '0.005679'  | '5.678900e-03' |    '0.567890%' |
|  0.056789    |   '0.056789'   |    '0.056789'  | '5.678900e-02' |    '5.678900%' |
|  0.56789     |   '0.56789'    |    '0.567890'  | '5.678900e-01' |   '56.789000%' |
|  5.6789      |   '5.6789'     |    '5.678900'  | '5.678900e+00' |  '567.890000%' |
| 56.789       |  '56.789'      |   '56.789000'  | '5.678900e+01' | '5678.900000%' |
+--------------+----------------+----------------+----------------+----------------+
```

```text
+--------------+----------------+----------------+----------------+----------------+
|              |  {<float>:.2}  |  {<float>:.2f} |  {<float>:.2e} |  {<float>:.2%} |
+--------------+----------------+----------------+----------------+----------------+
|  0.000056789 |    '5.7e-05'   |      '0.00'    |   '5.68e-05'   |      '0.01%'   |
|  0.00056789  |    '0.00057'   |      '0.00'    |   '5.68e-04'   |      '0.06%'   |
|  0.0056789   |    '0.0057'    |      '0.01'    |   '5.68e-03'   |      '0.57%'   |
|  0.056789    |    '0.057'     |      '0.06'    |   '5.68e-02'   |      '5.68%'   |
|  0.56789     |    '0.57'      |      '0.57'    |   '5.68e-01'   |     '56.79%'   |
|  5.6789      |    '5.7'       |      '5.68'    |   '5.68e+00'   |    '567.89%'   |
| 56.789       |    '5.7e+01'   |     '56.79'    |   '5.68e+01'   |   '5678.90%'   |
+--------------+----------------+----------------+----------------+----------------+
```

- **When both rounding up and rounding down are possible, the one that returns result with even last digit is chosen. That makes `'{6.5:.0f}'` a `'6'` and `'{7.5:.0f}'` an `'8'`.**
- **This rule only effects numbers that can be represented exactly by a float (`.5`, `.25`, …).**

### Ints

```python
{90:c}                                   # 'Z'
{90:b}                                   # '1011010'
{90:X}                                   # '5A'
```

**[🔼Back to Top](#table-of-contents)**

## Numbers

```python
<int>      = int(<float/str/bool>)                # Or: math.floor(<float>)
<float>    = float(<int/str/bool>)                # Or: <real>e±<int>
<complex>  = complex(real=0, imag=0)              # Or: <real> ± <real>j
<Fraction> = fractions.Fraction(0, 1)             # Or: Fraction(numerator=0, denominator=1)
<Decimal>  = decimal.Decimal(<str/int>)           # Or: Decimal((sign, digits, exponent))
```

- **`'int(<str>)'` and `'float(<str>)'` raise ValueError on malformed strings.**
- **Decimal numbers are stored exactly, unlike most floats where `'1.1 + 2.2 != 3.3'`.**
- **Floats can be compared with: `'math.isclose(<float>, <float>)'`.**
- **Precision of decimal operations is set with: `'decimal.getcontext().prec = <int>'`.**

### Basic Functions

```python
<num> = pow(<num>, <num>)                         # Or: <num> ** <num>
<num> = abs(<num>)                                # <float> = abs(<complex>)
<num> = round(<num> [, ±ndigits])                 # `round(126, -1) == 130`
```

### Math

```python
from math import e, pi, inf, nan, isinf, isnan    # `<el> == nan` is always False.
from math import sin, cos, tan, asin, acos, atan  # Also: degrees, radians.
from math import log, log10, log2                 # Log can accept base as second arg.
```

### Statistics

```python
from statistics import mean, median, variance     # Also: stdev, quantiles, groupby.
```

### Random

```python
from random import random, randint, choice        # Also shuffle, gauss, triangular, seed.
<float> = random()                                # A float inside [0, 1).
<int>   = randint(from_inc, to_inc)               # An int inside [from_inc, to_inc].
<el>    = choice(<sequence>)                      # Keeps the sequence intact.
```

### Bin, Hex

```python
<int> = ±0b<bin>                                  # Or: ±0x<hex>
<int> = int('±<bin>', 2)                          # Or: int('±<hex>', 16)
<int> = int('±0b<bin>', 0)                        # Or: int('±0x<hex>', 0)
<str> = bin(<int>)                                # Returns '[-]0b<bin>'.
```

### Bitwise Operators

```python
<int> = <int> & <int>                             # And (0b1100 & 0b1010 == 0b1000).
<int> = <int> | <int>                             # Or  (0b1100 | 0b1010 == 0b1110).
<int> = <int> ^ <int>                             # Xor (0b1100 ^ 0b1010 == 0b0110).
<int> = <int> << n_bits                           # Left shift. Use >> for right.
<int> = ~<int>                                    # Not. Also -<int> - 1.
```

**[🔼Back to Top](#table-of-contents)**

## Combinatorics

- **Every function returns an iterator.**
- **If you want to print the iterator, you need to pass it to the list() function first!**

```python
import itertools as it
```

```python
>>> it.product([0, 1], repeat=3)
[(0, 0, 0), (0, 0, 1), (0, 1, 0), (0, 1, 1),
 (1, 0, 0), (1, 0, 1), (1, 1, 0), (1, 1, 1)]
```

```python
>>> it.product('abc', 'abc')                      #   a  b  c
[('a', 'a'), ('a', 'b'), ('a', 'c'),              # a x  x  x
 ('b', 'a'), ('b', 'b'), ('b', 'c'),              # b x  x  x
 ('c', 'a'), ('c', 'b'), ('c', 'c')]              # c x  x  x
```

```python
>>> it.combinations('abc', 2)                     #   a  b  c
[('a', 'b'), ('a', 'c'),                          # a .  x  x
 ('b', 'c')]                                      # b .  .  x
```

```python
>>> it.combinations_with_replacement('abc', 2)    #   a  b  c
[('a', 'a'), ('a', 'b'), ('a', 'c'),              # a x  x  x
 ('b', 'b'), ('b', 'c'),                          # b .  x  x
 ('c', 'c')]                                      # c .  .  x
```

```python
>>> it.permutations('abc', 2)                     #   a  b  c
[('a', 'b'), ('a', 'c'),                          # a .  x  x
 ('b', 'a'), ('b', 'c'),                          # b x  .  x
 ('c', 'a'), ('c', 'b')]                          # c x  x  .
```

**[🔼Back to Top](#table-of-contents)**

## Datetime

- **Module 'datetime' provides 'date' `<D>`, 'time' `<T>`, 'datetime' `<DT>` and 'timedelta' `<TD>` classes. All are immutable and hashable.**
- **Time and datetime objects can be 'aware' `<a>`, meaning they have defined timezone, or 'naive' `<n>`, meaning they don't.**
- **If object is naive, it is presumed to be in the system's timezone.**

```python
from datetime import date, time, datetime, timedelta
from dateutil.tz import UTC, tzlocal, gettz, datetime_exists, resolve_imaginary
```

### Constructors

```python
<D>  = date(year, month, day)               # Only accepts valid dates from 1 to 9999 AD.
<T>  = time(hour=0, minute=0, second=0)     # Also: `microsecond=0, tzinfo=None, fold=0`.
<DT> = datetime(year, month, day, hour=0)   # Also: `minute=0, second=0, microsecond=0, …`.
<TD> = timedelta(weeks=0, days=0, hours=0)  # Also: `minutes=0, seconds=0, microsecond=0`.
```

- **Use `'<D/DT>.weekday()'` to get the day of the week as an int, with Monday being 0.**
- **`'fold=1'` means the second pass in case of time jumping back for one hour.**
- **Timedelta normalizes arguments to ±days, seconds (< 86 400) and microseconds (< 1M).**

### Now

```python
<D/DTn>  = D/DT.today()                     # Current local date or naive datetime.
<DTn>    = DT.utcnow()                      # Naive datetime from current UTC time.
<DTa>    = DT.now(<tzinfo>)                 # Aware datetime from current tz time.
```

- **To extract time use `'<DTn>.time()'`, `'<DTa>.time()'` or `'<DTa>.timetz()'`.**

### Timezone

```python
<tzinfo> = UTC                              # UTC timezone. London without DST.
<tzinfo> = tzlocal()                        # Local timezone. Also gettz().
<tzinfo> = gettz('<Continent>/<City>')      # 'Continent/City_Name' timezone or None.
<DTa>    = <DT>.astimezone(<tzinfo>)        # Datetime, converted to the passed timezone.
<Ta/DTa> = <T/DT>.replace(tzinfo=<tzinfo>)  # Unconverted object with a new timezone.
```

### Encode

```python
<D/T/DT> = D/T/DT.fromisoformat('<iso>')    # Object from ISO string. Raises ValueError.
<DT>     = DT.strptime(<str>, '<format>')   # Datetime from str, according to format.
<D/DTn>  = D/DT.fromordinal(<int>)          # D/DTn from days since the Gregorian NYE 1.
<DTn>    = DT.fromtimestamp(<real>)         # Local time DTn from seconds since the Epoch.
<DTa>    = DT.fromtimestamp(<real>, <tz.>)  # Aware datetime from seconds since the Epoch.
```

- **ISO strings come in following forms: `'YYYY-MM-DD'`, `'HH:MM:SS.mmmuuu[±HH:MM]'`, or both separated by an arbitrary character. All parts following hours are optional.**
- **Python uses the Unix Epoch: `'1970-01-01 00:00 UTC'`, `'1970-01-01 01:00 CET'`, ...**

### Decode

```python
<str>    = <D/T/DT>.isoformat(sep='T')      # Also: `timespec='auto/hours/minutes/seconds/…'`.
<str>    = <D/T/DT>.strftime('<format>')    # Custom string representation.
<int>    = <D/DT>.toordinal()               # Days since Gregorian NYE 1, ignoring time and tz.
<float>  = <DTn>.timestamp()                # Seconds since the Epoch, from DTn in local tz.
<float>  = <DTa>.timestamp()                # Seconds since the Epoch, from aware datetime.
```

### Format

```python
>>> dt = datetime.strptime('2015-05-14 23:39:00.00 +2000', '%Y-%m-%d %H:%M:%S.%f %z')
>>> dt.strftime("%A, %dth of %B '%y, %I:%M%p %Z")
"Thursday, 14th of May '15, 11:39PM UTC+02:00"
```

- **`'%Z'` only accepts `'UTC/GMT'` and local timezone's code. `'%z'` also accepts `'±HH:MM'`.**
- **For abbreviated weekday and month use `'%a'` and `'%b'`.**

### Arithmetics

```python
<D/DT>   = <D/DT>  ± <TD>                   # Returned datetime can fall into missing hour.
<TD>     = <D/DTn> - <D/DTn>                # Returns the difference, ignoring time jumps.
<TD>     = <DTa>   - <DTa>                  # Ignores time jumps if they share tzinfo object.
<TD>     = <TD>    * <real>                 # Also: <TD> = abs(<TD>) and <TD> = <TD> ±% <TD>.
<float>  = <TD>    / <TD>                   # How many weeks/years there are in TD. Also //.
```

**[🔼Back to Top](#table-of-contents)**

## Arguments

### Inside Function Call

```python
func(<positional_args>)                           # func(0, 0)
func(<keyword_args>)                              # func(x=0, y=0)
func(<positional_args>, <keyword_args>)           # func(0, y=0)
```

### Inside Function Definition

```python
def func(<nondefault_args>): ...                  # def func(x, y): ...
def func(<default_args>): ...                     # def func(x=0, y=0): ...
def func(<nondefault_args>, <default_args>): ...  # def func(x, y=0): ...
```

- **Default values are evaluated when function is first encountered in the scope.**
- **Any mutation of a mutable default value will persist between invocations.**

## Splat Operator

### Inside Function Call

**Splat expands a collection into positional arguments, while splatty-splat expands a dictionary into keyword arguments.**

```python
args   = (1, 2)
kwargs = {'x': 3, 'y': 4, 'z': 5}
func(*args, **kwargs)
```

#### Is the same as:

```python
func(1, 2, x=3, y=4, z=5)
```

### Inside Function Definition

**Splat combines zero or more positional arguments into a tuple, while splatty-splat combines zero or more keyword arguments into a dictionary.**

```python
def add(*a):
    return sum(a)
```

```python
>>> add(1, 2, 3)
6
```

#### Legal argument combinations:

```python
def f(*args): ...               # f(1, 2, 3)
def f(x, *args): ...            # f(1, 2, 3)
def f(*args, z): ...            # f(1, 2, z=3)
```

```python
def f(**kwargs): ...            # f(x=1, y=2, z=3)
def f(x, **kwargs): ...         # f(x=1, y=2, z=3) | f(1, y=2, z=3)
```

```python
def f(*args, **kwargs): ...     # f(x=1, y=2, z=3) | f(1, y=2, z=3) | f(1, 2, z=3) | f(1, 2, 3)
def f(x, *args, **kwargs): ...  # f(x=1, y=2, z=3) | f(1, y=2, z=3) | f(1, 2, z=3) | f(1, 2, 3)
def f(*args, y, **kwargs): ...  # f(x=1, y=2, z=3) | f(1, y=2, z=3)
```

```python
def f(*, x, y, z): ...          # f(x=1, y=2, z=3)
def f(x, *, y, z): ...          # f(x=1, y=2, z=3) | f(1, y=2, z=3)
def f(x, y, *, z): ...          # f(x=1, y=2, z=3) | f(1, y=2, z=3) | f(1, 2, z=3)
```

### Other Uses

```python
<list>  = [*<coll.> [, ...]]    # Or: list(<collection>) [+ ...]
<tuple> = (*<coll.>, [...])     # Or: tuple(<collection>) [+ ...]
<set>   = {*<coll.> [, ...]}    # Or: set(<collection>) [| ...]
<dict>  = {**<dict> [, ...]}    # Or: dict(**<dict> [, ...])
```

```python
head, *body, tail = <coll.>     # Head or tail can be omitted.
```

**[🔼Back to Top](#table-of-contents)**

## Inline

### Lambda

```python
<func> = lambda: <return_value>                     # A single statement function.
<func> = lambda <arg_1>, <arg_2>: <return_value>    # Also accepts default arguments.
```

### Comprehensions

```python
<list> = [i+1 for i in range(10)]                   # Or: [1, 2, ..., 10]
<iter> = (i for i in range(10) if i > 5)            # Or: iter([6, 7, 8, 9])
<set>  = {i+5 for i in range(10)}                   # Or: {5, 6, ..., 14}
<dict> = {i: i*2 for i in range(10)}                # Or: {0: 0, 1: 2, ..., 9: 18}
```

```python
>>> [l+r for l in 'abc' for r in 'abc']
['aa', 'ab', 'ac', ..., 'cc']
```

### Map, Filter, Reduce

```python
<iter> = map(lambda x: x + 1, range(10))            # Or: iter([1, 2, ..., 10])
<iter> = filter(lambda x: x > 5, range(10))         # Or: iter([6, 7, 8, 9])
<obj>  = reduce(lambda out, x: out + x, range(10))  # Or: 45
```

- **Reduce must be imported from the functools module.**

### Any, All

```python
<bool> = any(<collection>)                          # Is `bool(el)` True for any element.
<bool> = all(<collection>)                          # Is True for all elements or empty.
```

### Conditional Expression

```python
<obj> = <exp> if <condition> else <exp>             # Only one expression gets evaluated.
```

```python
>>> [a if a else 'zero' for a in (0, 1, 2, 3)]
['zero', 1, 2, 3]
```

### Named Tuple, Enum, Dataclass

```python
from collections import namedtuple
Point = namedtuple('Point', 'x y')                  # Creates a tuple's subclass.
point = Point(0, 0)                                 # Returns its instance.
```

```python
from enum import Enum
Direction = Enum('Direction', 'n e s w')            # Creates an enum.
direction = Direction.n                             # Returns its member.
```

```python
from dataclasses import make_dataclass
Player = make_dataclass('Player', ['loc', 'dir'])   # Creates a class.
player = Player(point, direction)                   # Returns its instance.
```

**[🔼Back to Top](#table-of-contents)**

## Imports

```python
import <module>            # Imports a built-in or '<module>.py'.
import <package>           # Imports a built-in or '<package>/__init__.py'.
import <package>.<module>  # Imports a built-in or '<package>/<module>.py'.
```

- **Package is a collection of modules, but it can also define its own objects.**
- **On a filesystem this corresponds to a directory of Python files with an optional init script.**
- **Running `'import <package>'` does not automatically provide access to the package's modules unless they are explicitly imported in its init script.**

## Closure

**We have/get a closure in Python when:**

- **A nested function references a value of its enclosing function and then**
- **the enclosing function returns the nested function.**

```python
def get_multiplier(a):
    def out(b):
        return a * b
    return out
```

```python
>>> multiply_by_3 = get_multiplier(3)
>>> multiply_by_3(10)
30
```

- **If multiple nested functions within enclosing function reference the same value, that value gets shared.**
- **To dynamically access function's first free variable use `'<function>.__closure__[0].cell_contents'`.**

### Partial

```python
from functools import partial
<function> = partial(<function> [, <arg_1>, <arg_2>, ...])
```

```python
>>> import operator as op
>>> multiply_by_3 = partial(op.mul, 3)
>>> multiply_by_3(10)
30
```

- **Partial is also useful in cases when function needs to be passed as an argument because it enables us to set its arguments beforehand.**
- **A few examples being: `'defaultdict(<function>)'`, `'iter(<function>, to_exclusive)'` and dataclass's `'field(default_factory=<function>)'`.**

### Non-Local

**If variable is being assigned to anywhere in the scope, it is regarded as a local variable, unless it is declared as a 'global' or a 'nonlocal'.**

```python
def get_counter():
    i = 0
    def out():
        nonlocal i
        i += 1
        return i
    return out
```

```python
>>> counter = get_counter()
>>> counter(), counter(), counter()
(1, 2, 3)
```

**[🔼Back to Top](#table-of-contents)**

## Decorator

- **A decorator takes a function, adds some functionality and returns it.**
- **It can be any [callable](#callable), but is usually implemented as a function that returns a [closure](#closure).**

```python
@decorator_name
def function_that_gets_passed_to_decorator():
    ...
```

### Debugger Example

**Decorator that prints function's name every time the function is called.**

```python
from functools import wraps

def debug(func):
    @wraps(func)
    def out(*args, **kwargs):
        print(func.__name__)
        return func(*args, **kwargs)
    return out

@debug
def add(x, y):
    return x + y
```

- **Wraps is a helper decorator that copies the metadata of the passed function (func) to the function it is wrapping (out).**
- **Without it `'add.__name__'` would return `'out'`.**

### LRU Cache

**Decorator that caches function's return values. All function's arguments must be hashable.**

```python
from functools import lru_cache

@lru_cache(maxsize=None)
def fib(n):
    return n if n < 2 else fib(n-2) + fib(n-1)
```

- **Default size of the cache is 128 values. Passing `'maxsize=None'` makes it unbounded.**
- **CPython interpreter limits recursion depth to 1000 by default. To increase it use `'sys.setrecursionlimit(<depth>)'`.**

### Parametrized Decorator

**A decorator that accepts arguments and returns a normal decorator that accepts a function.**

```python
from functools import wraps

def debug(print_result=False):
    def decorator(func):
        @wraps(func)
        def out(*args, **kwargs):
            result = func(*args, **kwargs)
            print(func.__name__, result if print_result else '')
            return result
        return out
    return decorator

@debug(print_result=True)
def add(x, y):
    return x + y
```

- **Using only `'@debug'` to decorate the add() function would not work here, because debug would then receive the add() function as a 'print_result' argument. Decorators can however manually check if the argument they received is a function and act accordingly.**

**[🔼Back to Top](#table-of-contents)**

## Class

```python
class <name>:
    def __init__(self, a):
        self.a = a
    def __repr__(self):
        class_name = self.__class__.__name__
        return f'{class_name}({self.a!r})'
    def __str__(self):
        return str(self.a)

    @classmethod
    def get_class_name(cls):
        return cls.__name__
```

- **Return value of repr() should be unambiguous and of str() readable.**
- **If only repr() is defined, it will also be used for str().**
- **Methods decorated with `'@staticmethod'` do not receive 'self' nor 'cls' as their first arg.**

#### Str() use cases:

```python
print(<el>)
f'{<el>}'
logging.warning(<el>)
csv.writer(<file>).writerow([<el>])
raise Exception(<el>)
```

#### Repr() use cases:

```python
print/str/repr([<el>])
f'{<el>!r}'
Z = dataclasses.make_dataclass('Z', ['a']); print/str/repr(Z(<el>))
>>> <el>
```

### Constructor Overloading

```python
class <name>:
    def __init__(self, a=None):
        self.a = a
```

### Inheritance

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age  = age

class Employee(Person):
    def __init__(self, name, age, staff_num):
        super().__init__(name, age)
        self.staff_num = staff_num
```

### Multiple Inheritance

```python
class A: pass
class B: pass
class C(A, B): pass
```

**MRO determines the order in which parent classes are traversed when searching for a method or an attribute:**

```python
>>> C.mro()
[<class 'C'>, <class 'A'>, <class 'B'>, <class 'object'>]
```

### Property

**Pythonic way of implementing getters and setters.**

```python
class Person:
    @property
    def name(self):
        return ' '.join(self._name)

    @name.setter
    def name(self, value):
        self._name = value.split()
```

```python
>>> person = Person()
>>> person.name = '\t Guido  van Rossum \n'
>>> person.name
'Guido van Rossum'
```

### Dataclass

**Decorator that automatically generates init(), repr() and eq() special methods.**

```python
from dataclasses import dataclass, field

@dataclass(order=False, frozen=False)
class <class_name>:
    <attr_name_1>: <type>
    <attr_name_2>: <type> = <default_value>
    <attr_name_3>: list/dict/set = field(default_factory=list/dict/set)
```

- **Objects can be made sortable with `'order=True'` and immutable with `'frozen=True'`.**
- **For object to be hashable, all attributes must be hashable and 'frozen' must be True.**
- **Function field() is needed because `'<attr_name>: list = []'` would make a list that is shared among all instances. Its 'default_factory' argument can be any [callable](#callable).**
- **For attributes of arbitrary type use `'typing.Any'`.**

#### Inline:

```python
from dataclasses import make_dataclass
<class> = make_dataclass('<class_name>', <coll_of_attribute_names>)
<class> = make_dataclass('<class_name>', <coll_of_tuples>)
<tuple> = ('<attr_name>', <type> [, <default_value>])
```

#### Rest of type annotations (CPython interpreter ignores them all):

```python
def func(<arg_name>: <type> [= <obj>]) -> <type>: ...
<var_name>: typing.List/Set/Iterable/Sequence/Optional[<type>]
<var_name>: typing.Dict/Tuple/Union[<type>, ...]
```

### Slots

**Mechanism that restricts objects to attributes listed in 'slots' and significantly reduces their memory footprint.**

```python
class MyClassWithSlots:
    __slots__ = ['a']
    def __init__(self):
        self.a = 1
```

### Copy

```python
from copy import copy, deepcopy
<object> = copy(<object>)
<object> = deepcopy(<object>)
```

**[🔼Back to Top](#table-of-contents)**

## Duck Types

**A duck type is an implicit type that prescribes a set of special methods. Any object that has those methods defined is considered a member of that duck type.**

### Comparable

- **If eq() method is not overridden, it returns `'id(self) == id(other)'`, which is the same as `'self is other'`.**
- **That means all objects compare not equal by default.**
- **Only the left side object has eq() method called, unless it returns NotImplemented, in which case the right object is consulted. False is returned if both return NotImplemented.**
- **Ne() automatically works on any object that has eq() defined.**

```python
class MyComparable:
    def __init__(self, a):
        self.a = a
    def __eq__(self, other):
        if isinstance(other, type(self)):
            return self.a == other.a
        return NotImplemented
```

### Hashable

- **Hashable object needs both hash() and eq() methods and its hash value should never change.**
- **Hashable objects that compare equal must have the same hash value, meaning default hash() that returns `'id(self)'` will not do.**
- **That is why Python automatically makes classes unhashable if you only implement eq().**

```python
class MyHashable:
    def __init__(self, a):
        self._a = a
    @property
    def a(self):
        return self._a
    def __eq__(self, other):
        if isinstance(other, type(self)):
            return self.a == other.a
        return NotImplemented
    def __hash__(self):
        return hash(self.a)
```

### Sortable

- **With 'total_ordering' decorator, you only need to provide eq() and one of lt(), gt(), le() or ge() special methods and the rest will be automatically generated.**
- **Functions sorted() and min() only require lt() method, while max() only requires gt(). However, it is best to define them all so that confusion doesn't arise in other contexts.**
- **When two lists, strings or dataclasses are compared, their values get compared in order until a pair of unequal values is found. The comparison of this two values is then returned. The shorter sequence is considered smaller in case of all values being equal.**

```python
from functools import total_ordering

@total_ordering
class MySortable:
    def __init__(self, a):
        self.a = a
    def __eq__(self, other):
        if isinstance(other, type(self)):
            return self.a == other.a
        return NotImplemented
    def __lt__(self, other):
        if isinstance(other, type(self)):
            return self.a < other.a
        return NotImplemented
```

### Iterator

- **Any object that has methods next() and iter() is an iterator.**
- **Next() should return next item or raise StopIteration.**
- **Iter() should return 'self'.**

```python
class Counter:
    def __init__(self):
        self.i = 0
    def __next__(self):
        self.i += 1
        return self.i
    def __iter__(self):
        return self
```

```python
>>> counter = Counter()
>>> next(counter), next(counter), next(counter)
(1, 2, 3)
```

#### Python has many different iterator objects:

- **Sequence iterators returned by the [iter()](#iterator) function, such as list_iterator and set_iterator.**
- **Objects returned by the [itertools](#itertools) module, such as count, repeat and cycle.**
- **Generators returned by the [generator functions](#generator) and [generator expressions](#comprehensions).**
- **File objects returned by the [open()](#open) function, etc.**

### Callable

- **All functions and classes have a call() method, hence are callable.**
- **When this cheatsheet uses `'<function>'` as an argument, it actually means `'<callable>'`.**

```python
class Counter:
    def __init__(self):
        self.i = 0
    def __call__(self):
        self.i += 1
        return self.i
```

```python
>>> counter = Counter()
>>> counter(), counter(), counter()
(1, 2, 3)
```

### Context Manager

- **Enter() should lock the resources and optionally return an object.**
- **Exit() should release the resources.**
- **Any exception that happens inside the with block is passed to the exit() method.**
- **If it wishes to suppress the exception it must return a true value.**

```python
class MyOpen:
    def __init__(self, filename):
        self.filename = filename
    def __enter__(self):
        self.file = open(self.filename)
        return self.file
    def __exit__(self, exc_type, exception, traceback):
        self.file.close()
```

```python
>>> with open('test.txt', 'w') as file:
...     file.write('Hello World!')
>>> with MyOpen('test.txt') as file:
...     print(file.read())
Hello World!
```

## Iterable Duck Types

### Iterable

- **Only required method is iter(). It should return an iterator of object's items.**
- **Contains() automatically works on any object that has iter() defined.**

```python
class MyIterable:
    def __init__(self, a):
        self.a = a
    def __iter__(self):
        return iter(self.a)
    def __contains__(self, el):
        return el in self.a
```

```python
>>> obj = MyIterable([1, 2, 3])
>>> [el for el in obj]
[1, 2, 3]
>>> 1 in obj
True
```

### Collection

- **Only required methods are iter() and len(). Len() should return the number of items.**
- **This cheatsheet actually means `'<iterable>'` when it uses `'<collection>'`.**
- **I chose not to use the name 'iterable' because it sounds scarier and more vague than 'collection'. The only drawback of this decision is that a reader could think a certain function doesn't accept iterators when it does, since iterators are the only built-in objects that are iterable but are not collections.**

```python
class MyCollection:
    def __init__(self, a):
        self.a = a
    def __iter__(self):
        return iter(self.a)
    def __contains__(self, el):
        return el in self.a
    def __len__(self):
        return len(self.a)
```

### Sequence

- **Only required methods are len() and getitem().**
- **Getitem() should return an item at the passed index or raise IndexError.**
- **Iter() and contains() automatically work on any object that has getitem() defined.**
- **Reversed() automatically works on any object that has len() and getitem() defined.**

```python
class MySequence:
    def __init__(self, a):
        self.a = a
    def __iter__(self):
        return iter(self.a)
    def __contains__(self, el):
        return el in self.a
    def __len__(self):
        return len(self.a)
    def __getitem__(self, i):
        return self.a[i]
    def __reversed__(self):
        return reversed(self.a)
```

#### Discrepancies between glossary definitions and abstract base classes:

- **Glossary defines iterable as any object with iter() or getitem() and sequence as any object with getitem() and len(). It does not define collection.**
- **Passing ABC Iterable to isinstance() or issubclass() checks whether object/class has method iter(), while ABC Collection checks for iter(), contains() and len().**

### ABC Sequence

- **It's a richer interface than the basic sequence.**
- **Extending it generates iter(), contains(), reversed(), index() and count().**
- **Unlike `'abc.Iterable'` and `'abc.Collection'`, it is not a duck type. That is why `'issubclass(MySequence, abc.Sequence)'` would return False even if MySequence had all the methods defined. It however recognizes list, tuple, range, str, bytes, bytearray, memoryview and deque, because they are registered as Sequence's virtual subclasses.**

```python
from collections import abc

class MyAbcSequence(abc.Sequence):
    def __init__(self, a):
        self.a = a
    def __len__(self):
        return len(self.a)
    def __getitem__(self, i):
        return self.a[i]
```

#### Table of required and automatically available special methods:

```text
+------------+------------+------------+------------+--------------+
|            |  Iterable  | Collection |  Sequence  | abc.Sequence |
+------------+------------+------------+------------+--------------+
| iter()     |    REQ     |    REQ     |    Yes     |     Yes      |
| contains() |    Yes     |    Yes     |    Yes     |     Yes      |
| len()      |            |    REQ     |    REQ     |     REQ      |
| getitem()  |            |            |    REQ     |     REQ      |
| reversed() |            |            |    Yes     |     Yes      |
| index()    |            |            |            |     Yes      |
| count()    |            |            |            |     Yes      |
+------------+------------+------------+------------+--------------+
```

- **Other ABCs that generate missing methods are: MutableSequence, Set, MutableSet, Mapping and MutableMapping.**
- **Names of their required methods are stored in `'<abc>.__abstractmethods__'`.**

**[🔼Back to Top](#table-of-contents)**

## Enum

```python
from enum import Enum, auto
```

```python
class <enum_name>(Enum):
    <member_name_1> = <value_1>
    <member_name_2> = <value_2_a>, <value_2_b>
    <member_name_3> = auto()
```

- **If there are no numeric values before auto(), it returns 1.**
- **Otherwise it returns an increment of the last numeric value.**

```python
<member> = <enum>.<member_name>                 # Returns a member.
<member> = <enum>['<member_name>']              # Returns a member or raises KeyError.
<member> = <enum>(<value>)                      # Returns a member or raises ValueError.
<str>    = <member>.name                        # Returns member's name.
<obj>    = <member>.value                       # Returns member's value.
```

```python
list_of_members = list(<enum>)
member_names    = [a.name for a in <enum>]
member_values   = [a.value for a in <enum>]
random_member   = random.choice(list(<enum>))
```

```python
def get_next_member(member):
    members = list(member.__class__)
    index   = (members.index(member) + 1) % len(members)
    return members[index]
```

### Inline

```python
Cutlery = Enum('Cutlery', 'fork knife spoon')
Cutlery = Enum('Cutlery', ['fork', 'knife', 'spoon'])
Cutlery = Enum('Cutlery', {'fork': 1, 'knife': 2, 'spoon': 3})
```

#### User-defined functions cannot be values, so they must be wrapped:

```python
from functools import partial
LogicOp = Enum('LogicOp', {'AND': partial(lambda l, r: l and r),
                           'OR':  partial(lambda l, r: l or r)})
```

- **Member names are in all caps because trying to access a member that is named after a reserved keyword raises SyntaxError.**

**[🔼Back to Top](#table-of-contents)**

## Exceptions

```python
try:
    <code>
except <exception>:
    <code>
```

### Complex Example

```python
try:
    <code_1>
except <exception_a>:
    <code_2_a>
except <exception_b>:
    <code_2_b>
else:
    <code_2_c>
finally:
    <code_3>
```

- **Code inside the `'else'` block will only be executed if `'try'` block had no exceptions.**
- **Code inside the `'finally'` block will always be executed (unless a signal is received).**

### Catching Exceptions

```python
except <exception>: ...
except <exception> as <name>: ...
except (<exception>, [...]): ...
except (<exception>, [...]) as <name>: ...
```

- **Also catches subclasses of the exception.**
- **Use `'traceback.print_exc()'` to print the error message to stderr.**
- **Use `'print(<name>)'` to print just the cause of the exception (its arguments).**
- **Use `'logging.exception(<message>)'` to log the exception.**

### Raising Exceptions

```python
raise <exception>
raise <exception>()
raise <exception>(<el> [, ...])
```

#### Re-raising caught exception:

```python
except <exception> as <name>:
    ...
    raise
```

### Exception Object

```python
arguments = <name>.args
exc_type  = <name>.__class__
filename  = <name>.__traceback__.tb_frame.f_code.co_filename
func_name = <name>.__traceback__.tb_frame.f_code.co_name
line      = linecache.getline(filename, <name>.__traceback__.tb_lineno)
traceback = ''.join(traceback.format_tb(<name>.__traceback__))
error_msg = ''.join(traceback.format_exception(exc_type, <name>, <name>.__traceback__))
```

### Built-in Exceptions

```text
BaseException
 +-- SystemExit                   # Raised by the sys.exit() function.
 +-- KeyboardInterrupt            # Raised when the user hits the interrupt key (ctrl-c).
 +-- Exception                    # User-defined exceptions should be derived from this class.
      +-- ArithmeticError         # Base class for arithmetic errors.
      |    +-- ZeroDivisionError  # Raised when dividing by zero.
      +-- AssertionError          # Raised by `assert <exp>` if expression returns false value.
      +-- AttributeError          # Raised when an attribute is missing.
      +-- EOFError                # Raised by input() when it hits end-of-file condition.
      +-- LookupError             # Raised when a look-up on a collection fails.
      |    +-- IndexError         # Raised when a sequence index is out of range.
      |    +-- KeyError           # Raised when a dictionary key or set element is missing.
      +-- MemoryError             # Out of memory. Could be too late to start deleting vars.
      +-- NameError               # Raised when an object is missing.
      +-- OSError                 # Errors such as “file not found” or “disk full” (see Open).
      |    +-- FileNotFoundError  # When a file or directory is requested but doesn't exist.
      +-- RuntimeError            # Raised by errors that don't fall into other categories.
      |    +-- RecursionError     # Raised when the maximum recursion depth is exceeded.
      +-- StopIteration           # Raised by next() when run on an empty iterator.
      +-- TypeError               # Raised when an argument is of wrong type.
      +-- ValueError              # When an argument is of right type but inappropriate value.
           +-- UnicodeError       # Raised when encoding/decoding strings to/from bytes fails.
```

#### Collections and their exceptions:

```text
+-----------+------------+------------+------------+
|           |    List    |    Set     |    Dict    |
+-----------+------------+------------+------------+
| getitem() | IndexError |            |  KeyError  |
| pop()     | IndexError |  KeyError  |  KeyError  |
| remove()  | ValueError |  KeyError  |            |
| index()   | ValueError |            |            |
+-----------+------------+------------+------------+
```

#### Useful built-in exceptions:

```python
raise TypeError('Argument is of wrong type!')
raise ValueError('Argument is of right type but inappropriate value!')
raise RuntimeError('None of above!')
```

### User-defined Exceptions

```python
class MyError(Exception): pass
class MyInputError(MyError): pass
```

**[🔼Back to Top](#table-of-contents)**

## Exit

**Exits the interpreter by raising SystemExit exception.**

```python
import sys
sys.exit()                        # Exits with exit code 0 (success).
sys.exit(<el>)                    # Prints to stderr and exits with 1.
sys.exit(<int>)                   # Exits with passed exit code.
```

**[🔼Back to Top](#table-of-contents)**

## Print

```python
print(<el_1>, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
```

- **Use `'file=sys.stderr'` for messages about errors.**
- **Use `'flush=True'` to forcibly flush the stream.**

### Pretty Print

```python
from pprint import pprint
pprint(<collection>, width=80, depth=None, compact=False, sort_dicts=True)
```

- **Levels deeper than 'depth' get replaced by '...'.**

**[🔼Back to Top](#table-of-contents)**

## Input

**Reads a line from user input or pipe if present.**

```python
<str> = input(prompt=None)
```

- **Trailing newline gets stripped.**
- **Prompt string is printed to the standard output before reading input.**
- **Raises EOFError when user hits EOF (ctrl-d/ctrl-z⏎) or input stream gets exhausted.**

**[🔼Back to Top](#table-of-contents)**

## Command Line Arguments

```python
import sys
scripts_path = sys.argv[0]
arguments    = sys.argv[1:]
```

### Argument Parser

```python
from argparse import ArgumentParser, FileType
p = ArgumentParser(description=<str>)
p.add_argument('-<short_name>', '--<name>', action='store_true')  # Flag.
p.add_argument('-<short_name>', '--<name>', type=<type>)          # Option.
p.add_argument('<name>', type=<type>, nargs=1)                    # First argument.
p.add_argument('<name>', type=<type>, nargs='+')                  # Remaining arguments.
p.add_argument('<name>', type=<type>, nargs='*')                  # Optional arguments.
args  = p.parse_args()                                            # Exits on error.
value = args.<name>
```

- **Use `'help=<str>'` to set argument description that will be displayed in help message.**
- **Use `'default=<el>'` to set the default value.**
- **Use `'type=FileType(<mode>)'` for files. Accepts 'encoding', but 'newline' is None.**

**[🔼Back to Top](#table-of-contents)**

## Open

**Opens the file and returns a corresponding file object.**

```python
<file> = open(<path>, mode='r', encoding=None, newline=None)
```

- **`'encoding=None'` means that the default encoding is used, which is platform dependent. Best practice is to use `'encoding="utf-8"'` whenever possible.**
- **`'newline=None'` means all different end of line combinations are converted to '\n' on read, while on write all '\n' characters are converted to system's default line separator.**
- **`'newline=""'` means no conversions take place, but input is still broken into chunks by readline() and readlines() on every '\n', '\r' and '\r\n'.**

### Modes

- **`'r'` - Read (default).**
- **`'w'` - Write (truncate).**
- **`'x'` - Write or fail if the file already exists.**
- **`'a'` - Append.**
- **`'w+'` - Read and write (truncate).**
- **`'r+'` - Read and write from the start.**
- **`'a+'` - Read and write from the end.**
- **`'t'` - Text mode (default).**
- **`'b'` - Binary mode (`'br'`, `'bw'`, `'bx'`, …).**

### Exceptions

- **`'FileNotFoundError'` can be raised when reading with `'r'` or `'r+'`.**
- **`'FileExistsError'` can be raised when writing with `'x'`.**
- **`'IsADirectoryError'` and `'PermissionError'` can be raised by any.**
- **`'OSError'` is the parent class of all listed exceptions.**

### File Object

```python
<file>.seek(0)                      # Moves to the start of the file.
<file>.seek(offset)                 # Moves 'offset' chars/bytes from the start.
<file>.seek(0, 2)                   # Moves to the end of the file.
<bin_file>.seek(±offset, <anchor>)  # Anchor: 0 start, 1 current position, 2 end.
```

```python
<str/bytes> = <file>.read(size=-1)  # Reads 'size' chars/bytes or until EOF.
<str/bytes> = <file>.readline()     # Returns a line or empty string/bytes on EOF.
<list>      = <file>.readlines()    # Returns a list of remaining lines.
<str/bytes> = next(<file>)          # Returns a line using buffer. Do not mix.
```

```python
<file>.write(<str/bytes>)           # Writes a string or bytes object.
<file>.writelines(<collection>)     # Writes a coll. of strings or bytes objects.
<file>.flush()                      # Flushes write buffer. Runs every 4096/8192 B.
```

- **Methods do not add or strip trailing newlines, even writelines().**

### Read Text from File

```python
def read_file(filename):
    with open(filename, encoding='utf-8') as file:
        return file.readlines()
```

### Write Text to File

```python
def write_to_file(filename, text):
    with open(filename, 'w', encoding='utf-8') as file:
        file.write(text)
```

**[🔼Back to Top](#table-of-contents)**

## Paths

```python
from os import getcwd, path, listdir, scandir
from glob import glob
```

```python
<str>  = getcwd()                   # Returns the current working directory.
<str>  = path.join(<path>, ...)     # Joins two or more pathname components.
<str>  = path.abspath(<path>)       # Returns absolute path.
```

```python
<str>  = path.basename(<path>)      # Returns final component of the path.
<str>  = path.dirname(<path>)       # Returns path without the final component.
<tup.> = path.splitext(<path>)      # Splits on last period of the final component.
```

```python
<list> = listdir(path='.')          # Returns filenames located at path.
<list> = glob('<pattern>')          # Returns paths matching the wildcard pattern.
```

```python
<bool> = path.exists(<path>)        # Or: <Path>.exists()
<bool> = path.isfile(<path>)        # Or: <DirEntry/Path>.is_file()
<bool> = path.isdir(<path>)         # Or: <DirEntry/Path>.is_dir()
```

```python
<stat> = os.stat(<path>)            # Or: <DirEntry/Path>.stat()
<real> = <stat>.st_mtime/st_size/…  # Modification time, size in bytes, …
```

### DirEntry

**Unlike listdir(), scandir() returns DirEntry objects that cache isfile, isdir and on Windows also stat information, thus significantly increasing the performance of code that requires it.**

```python
<iter> = scandir(path='.')          # Returns DirEntry objects located at path.
<str>  = <DirEntry>.path            # Returns whole path as a string.
<str>  = <DirEntry>.name            # Returns final component as a string.
<file> = open(<DirEntry>)           # Opens the file and returns a file object.
```

### Path Object

```python
from pathlib import Path
```

```python
<Path> = Path(<path> [, ...])       # Accepts strings, Paths and DirEntry objects.
<Path> = <path> / <path> [/ ...]    # First or second path must be a Path object.
```

```python
<Path> = Path()                     # Returns relative cwd. Also Path('.').
<Path> = Path.cwd()                 # Returns absolute cwd. Also Path().resolve().
<Path> = Path.home()                # Returns user's home directory (absolute).
<Path> = Path(__file__).resolve()   # Returns script's path if cwd wasn't changed.
```

```python
<Path> = <Path>.parent              # Returns Path without the final component.
<str>  = <Path>.name                # Returns final component as a string.
<str>  = <Path>.stem                # Returns final component without extension.
<str>  = <Path>.suffix              # Returns final component's extension.
<tup.> = <Path>.parts               # Returns all components as strings.
```

```python
<iter> = <Path>.iterdir()           # Returns directory contents as Path objects.
<iter> = <Path>.glob('<pattern>')   # Returns Paths matching the wildcard pattern.
```

```python
<str>  = str(<Path>)                # Returns path as a string.
<file> = open(<Path>)               # Also <Path>.read/write_text/bytes().
```

**[🔼Back to Top](#table-of-contents)**

## OS Commands

```python
import os, shutil, subprocess
```

```python
os.chdir(<path>)                    # Changes the current working directory.
os.mkdir(<path>, mode=0o777)        # Creates a directory. Permissions are in octal.
os.makedirs(<path>, mode=0o777)     # Creates all path's dirs. Also: `exist_ok=False`.
```

```python
shutil.copy(from, to)               # Copies the file. 'to' can exist or be a dir.
shutil.copytree(from, to)           # Copies the directory. 'to' must not exist.
```

```python
os.rename(from, to)                 # Renames/moves the file or directory.
os.replace(from, to)                # Same, but overwrites 'to' if it exists.
```

```python
os.remove(<path>)                   # Deletes the file.
os.rmdir(<path>)                    # Deletes the empty directory.
shutil.rmtree(<path>)               # Deletes the directory.
```

- **Paths can be either strings, Paths or DirEntry objects.**
- **Functions report OS related errors by raising either OSError or one of its [subclasses](#exceptions-1).**

### Shell Commands

```python
<pipe> = os.popen('<command>')      # Executes command in sh/cmd. Returns its stdout pipe.
<str>  = <pipe>.read(size=-1)       # Reads 'size' chars or until EOF. Also readline/s().
<int>  = <pipe>.close()             # Closes the pipe. Returns None on success.
```

#### Sends '1 + 1' to the basic calculator and captures its output:

```python
>>> subprocess.run('bc', input='1 + 1\n', capture_output=True, text=True)
CompletedProcess(args='bc', returncode=0, stdout='2\n', stderr='')
```

#### Sends test.in to the basic calculator running in standard mode and saves its output to test.out:

```python
>>> from shlex import split
>>> os.popen('echo 1 + 1 > test.in')
>>> subprocess.run(split('bc -s'), stdin=open('test.in'), stdout=open('test.out', 'w'))
CompletedProcess(args=['bc', '-s'], returncode=0)
>>> open('test.out').read()
'2\n'
```

**[🔼Back to Top](#table-of-contents)**

## JSON

**Text file format for storing collections of strings and numbers.**

```python
import json
<str>    = json.dumps(<object>)     # Converts object to JSON string.
<object> = json.loads(<str>)        # Converts JSON string to object.
```

### Read Object from JSON File

```python
def read_json_file(filename):
    with open(filename, encoding='utf-8') as file:
        return json.load(file)
```

### Write Object to JSON File

```python
def write_to_json_file(filename, an_object):
    with open(filename, 'w', encoding='utf-8') as file:
        json.dump(an_object, file, ensure_ascii=False, indent=2)
```

**[🔼Back to Top](#table-of-contents)**

## Pickle

**Binary file format for storing Python objects.**

```python
import pickle
<bytes>  = pickle.dumps(<object>)   # Converts object to bytes object.
<object> = pickle.loads(<bytes>)    # Converts bytes object to object.
```

### Read Object from File

```python
def read_pickle_file(filename):
    with open(filename, 'rb') as file:
        return pickle.load(file)
```

### Write Object to File

```python
def write_to_pickle_file(filename, an_object):
    with open(filename, 'wb') as file:
        pickle.dump(an_object, file)
```

**[🔼Back to Top](#table-of-contents)**

## CSV

**Text file format for storing spreadsheets.**

```python
import csv
```

### Read

```python
<reader> = csv.reader(<file>)       # Also: `dialect='excel', delimiter=','`.
<list>   = next(<reader>)           # Returns next row as a list of strings.
<list>   = list(<reader>)           # Returns a list of remaining rows.
```

- **File must be opened with a `'newline=""'` argument, or newlines embedded inside quoted fields will not be interpreted correctly!**
- **To print the spreadsheet to the console use [Tabulate](#table) library.**
- **For XML and binary Excel files (xlsx, xlsm and xlsb) use [Pandas](#dataframe-plot-encode-decode) library.**

### Write

```python
<writer> = csv.writer(<file>)       # Also: `dialect='excel', delimiter=','`.
<writer>.writerow(<collection>)     # Encodes objects using `str(<el>)`.
<writer>.writerows(<coll_of_coll>)  # Appends multiple rows.
```

- **File must be opened with a `'newline=""'` argument, or '\r' will be added in front of every '\n' on platforms that use '\r\n' line endings!**

### Parameters

- **`'dialect'` - Master parameter that sets the default values. String or a Dialect object.**
- **`'delimiter'` - A one-character string used to separate fields.**
- **`'quotechar'` - Character for quoting fields that contain special characters.**
- **`'doublequote'` - Whether quotechars inside fields are/get doubled or escaped.**
- **`'skipinitialspace'` - Is space character at the start of the field stripped by the reader.**
- **`'lineterminator'` - How writer terminates rows. Reader is hardcoded to '\n', '\r', '\r\n'.**
- **`'quoting'` - 0: As necessary, 1: All, 2: All but numbers which are read as floats, 3: None.**
- **`'escapechar'` - Character for escaping quotechars if doublequote is False.**

### Dialects

```text
+------------------+--------------+--------------+--------------+
|                  |     excel    |   excel-tab  |     unix     |
+------------------+--------------+--------------+--------------+
| delimiter        |       ','    |      '\t'    |       ','    |
| quotechar        |       '"'    |       '"'    |       '"'    |
| doublequote      |      True    |      True    |      True    |
| skipinitialspace |     False    |     False    |     False    |
| lineterminator   |    '\r\n'    |    '\r\n'    |      '\n'    |
| quoting          |         0    |         0    |         1    |
| escapechar       |      None    |      None    |      None    |
+------------------+--------------+--------------+--------------+
```

### Read Rows from CSV File

```python
def read_csv_file(filename, dialect='excel'):
    with open(filename, encoding='utf-8', newline='') as file:
        return list(csv.reader(file, dialect))
```

### Write Rows to CSV File

```python
def write_to_csv_file(filename, rows, dialect='excel'):
    with open(filename, 'w', encoding='utf-8', newline='') as file:
        writer = csv.writer(file, dialect)
        writer.writerows(rows)
```

**[🔼Back to Top](#table-of-contents)**

## SQLite

**A server-less database engine that stores each database into a separate file.**

```python
import sqlite3
<conn> = sqlite3.connect(<path>)                # Opens existing or new file. Also ':memory:'.
<conn>.close()                                  # Closes the connection.
```

### Read

```python
<cursor> = <conn>.execute('<query>')            # Can raise a subclass of sqlite3.Error.
<tuple>  = <cursor>.fetchone()                  # Returns next row. Also next(<cursor>).
<list>   = <cursor>.fetchall()                  # Returns remaining rows. Also list(<cursor>).
```

### Write

```python
<conn>.execute('<query>')                       # Can raise a subclass of sqlite3.Error.
<conn>.commit()                                 # Saves all changes since the last commit.
<conn>.rollback()                               # Discards all changes since the last commit.
```

#### Or:

```python
with <conn>:                                    # Exits the block with commit() or rollback(),
    <conn>.execute('<query>')                   # depending on whether any exception occurred.
```

### Placeholders

```python
<conn>.execute('<query>', <list/tuple>)         # Replaces '?'s in query with values.
<conn>.execute('<query>', <dict/namedtuple>)    # Replaces ':<key>'s with values.
<conn>.executemany('<query>', <coll_of_above>)  # Runs execute() multiple times.
```

- **Passed values can be of type str, int, float, bytes, None, bool, datetime.date or datetime.datetime.**
- **Bools will be stored and returned as ints and dates as [ISO formatted strings](#encode).**

### Example

**Values are not actually saved in this example because `'conn.commit()'` is omitted!**

```python
>>> conn = sqlite3.connect('test.db')
>>> conn.execute('CREATE TABLE person (person_id INTEGER PRIMARY KEY, name, height)')
>>> conn.execute('INSERT INTO person VALUES (NULL, ?, ?)', ('Jean-Luc', 187)).lastrowid
1
>>> conn.execute('SELECT * FROM person').fetchall()
[(1, 'Jean-Luc', 187)]
```

### SqlAlchemy

```python
# $ pip3 install sqlalchemy
from sqlalchemy import create_engine, text
<engine> = create_engine('<url>').connect()     # Url: 'dialect://user:password@host/dbname'.
<conn>   = <engine>.connect()                   # Creates a connection. Also <conn>.close().
<cursor> = <conn>.execute(text('<query>'), …)   # Replaces ':<key>'s with keyword arguments.
with <conn>.begin(): ...                        # Exits the block with commit or rollback.
```

```text
+------------+--------------+-----------+-----------------------------------+
| Dialects   | pip3 install | import    | Dependencies                      |
+------------+--------------+-----------+-----------------------------------+
| mysql      | mysqlclient  | MySQLdb   | www.pypi.org/project/mysqlclient  |
| postgresql | psycopg2     | psycopg2  | www.psycopg.org/docs/install.html |
| mssql      | pyodbc       | pyodbc    | apt install g++ unixodbc-dev      |
| oracle     | cx_oracle    | cx_Oracle | Oracle Instant Client             |
+------------+--------------+-----------+-----------------------------------+
```

**[🔼Back to Top](#table-of-contents)**

## Bytes

**Bytes object is an immutable sequence of single bytes. Mutable version is called bytearray.**

```python
<bytes> = b'<str>'                          # Only accepts ASCII characters and \x00-\xff.
<int>   = <bytes>[<index>]                  # Returns an int in range from 0 to 255.
<bytes> = <bytes>[<slice>]                  # Returns bytes even if it has only one element.
<bytes> = <bytes>.join(<coll_of_bytes>)     # Joins elements using bytes as a separator.
```

### Encode

```python
<bytes> = bytes(<coll_of_ints>)             # Ints must be in range from 0 to 255.
<bytes> = bytes(<str>, 'utf-8')             # Or: <str>.encode('utf-8')
<bytes> = <int>.to_bytes(n_bytes, …)        # `byteorder='little/big', signed=False`.
<bytes> = bytes.fromhex('<hex>')            # Hex pairs can be separated by whitespaces.
```

### Decode

```python
<list>  = list(<bytes>)                     # Returns ints in range from 0 to 255.
<str>   = str(<bytes>, 'utf-8')             # Or: <bytes>.decode('utf-8')
<int>   = int.from_bytes(<bytes>, …)        # `byteorder='little/big', signed=False`.
'<hex>' = <bytes>.hex()                     # Returns hex pairs. Accepts `sep=<str>`.
```

### Read Bytes from File

```python
def read_bytes(filename):
    with open(filename, 'rb') as file:
        return file.read()
```

### Write Bytes to File

```python
def write_bytes(filename, bytes_obj):
    with open(filename, 'wb') as file:
        file.write(bytes_obj)
```

**[🔼Back to Top](#table-of-contents)**

## Struct

- **Module that performs conversions between a sequence of numbers and a bytes object.**
- **System’s type sizes, byte order, and alignment rules are used by default.**

```python
from struct import pack, unpack
<bytes> = pack('<format>', <el_1> [, ...])  # Packages arguments into bytes object.
<tuple> = unpack('<format>', <bytes>)       # Use iter_unpack() for iterator of tuples.
```

```python
>>> pack('>hhl', 1, 2, 3)
b'\x00\x01\x00\x02\x00\x00\x00\x03'
>>> unpack('>hhl', b'\x00\x01\x00\x02\x00\x00\x00\x03')
(1, 2, 3)
```

### Format

#### For standard type sizes and manual alignment (padding) start format string with:

- **`'='` - System's byte order (usually little-endian).**
- **`'<'` - Little-endian.**
- **`'>'` - Big-endian (also `'!'`).**

#### Besides numbers, pack() and unpack() also support bytes objects as part of the sequence:

- **`'c'` - A bytes object with a single element. For pad byte use `'x'`.**
- **`'<n>s'` - A bytes object with n elements.**

#### Integer types. Use a capital letter for unsigned type. Minimum and standard sizes are in brackets:

- **`'b'` - char (1/1)**
- **`'h'` - short (2/2)**
- **`'i'` - int (2/4)**
- **`'l'` - long (4/4)**
- **`'q'` - long long (8/8)**

#### Floating point types:

- **`'f'` - float (4/4)**
- **`'d'` - double (8/8)**

**[🔼Back to Top](#table-of-contents)**

## Array

**List that can only hold numbers of a predefined type. Available types and their minimum sizes in bytes are listed above. Sizes and byte order are always determined by the system.**

```python
from array import array
<array> = array('<typecode>', <collection>)    # Array from collection of numbers.
<array> = array('<typecode>', <bytes>)         # Array from bytes object.
<array> = array('<typecode>', <array>)         # Treats array as a sequence of numbers.
<bytes> = bytes(<array>)                       # Or: <array>.tobytes()
<file>.write(<array>)                          # Writes array to the binary file.
```

**[🔼Back to Top](#table-of-contents)**

## Memory View

- **A sequence object that points to the memory of another object.**
- **Each element can reference a single or multiple consecutive bytes, depending on format.**
- **Order and number of elements can be changed with slicing.**
- **Casting only works between char and other types and uses system's sizes.**
- **Byte order is always determined by the system.**

```python
<mview> = memoryview(<bytes/bytearray/array>)  # Immutable if bytes, else mutable.
<real>  = <mview>[<index>]                     # Returns an int or a float.
<mview> = <mview>[<slice>]                     # Mview with rearranged elements.
<mview> = <mview>.cast('<typecode>')           # Casts memoryview to the new format.
<mview>.release()                              # Releases the object's memory buffer.
```

### Decode

```python
<bytes> = bytes(<mview>)                       # Returns a new bytes object.
<bytes> = <bytes>.join(<coll_of_mviews>)       # Joins mviews using bytes object as sep.
<array> = array('<typecode>', <mview>)         # Treats mview as a sequence of numbers.
<file>.write(<mview>)                          # Writes mview to the binary file.
```

```python
<list>  = list(<mview>)                        # Returns a list of ints or floats.
<str>   = str(<mview>, 'utf-8')                # Treats mview as a bytes object.
<int>   = int.from_bytes(<mview>, …)           # `byteorder='little/big', signed=False`.
'<hex>' = <mview>.hex()                        # Treats mview as a bytes object.
```

**[🔼Back to Top](#table-of-contents)**

## Deque

**A thread-safe list with efficient appends and pops from either side. Pronounced "deck".**

```python
from collections import deque
<deque> = deque(<collection>, maxlen=None)
```

```python
<deque>.appendleft(<el>)                       # Opposite element is dropped if full.
<deque>.extendleft(<collection>)               # Collection gets reversed.
<el> = <deque>.popleft()                       # Raises IndexError if empty.
<deque>.rotate(n=1)                            # Rotates elements to the right.
```

**[🔼Back to Top](#table-of-contents)**

# Functions

## Lambda

**Anonymous function that can only contain a single expression.**

```python
<lambda> = lambda <arg_1> [, ...]: <expr>     # Returns a function object.
```

```python
>>> (lambda x, y: x + y)(1, 2)
3
```

**[🔼Back to Top](#table-of-contents)**

## Map

**Applies a function to each element of a collection.**

```python
<map> = map(<func>, <collection>)             # Returns a map object.
```

```python
>>> list(map(lambda x: x + 1, [1, 2, 3]))
[2, 3, 4]
```

**[🔼Back to Top](#table-of-contents)**

## Filter

**Returns a collection of elements that satisfy a condition.**

```python
<filter> = filter(<func>, <collection>)       # Returns a filter object.
```

```python
>>> list(filter(lambda x: x > 2, [1, 2, 3]))
[3]
```

**[🔼Back to Top](#table-of-contents)**

## Reduce

**Applies a function to the first two elements of a collection, then to the result and the next element, and so on.**

```python

from functools import reduce
<el> = reduce(<func>, <collection>)           # Returns a single element.
```

```python
>>> reduce(lambda x, y: x + y, [1, 2, 3])

6
```

**[🔼Back to Top](#table-of-contents)**

## Zip

**Returns a collection of tuples, where each tuple contains the i-th element from each of the argument sequences or iterables.**

```python

<zip> = zip(<collection_1>, <collection_2>)   # Returns a zip object.
```

```python
>>> list(zip([1, 2, 3], [4, 5, 6]))
[(1, 4), (2, 5), (3, 6)]
```

**[🔼Back to Top](#table-of-contents)**

## Partial

**Returns a new function with some of the arguments already set.**

```python
from functools import partial
<func> = partial(<func>, <arg_1> [, ...])     # Returns a function object.
```

```python
>>> from functools import partial
>>> def add(x, y):
...     return x + y
...
>>> add_1 = partial(add, 1)
>>> add_1(2)
3
```

**[🔼Back to Top](#table-of-contents)**

## Compose

**Returns a function that is the composition of a list of functions, where each function consumes the return value of the function that follows.**

```python
from functools import reduce
<func> = reduce(lambda f, g: lambda x: f(g(x)), <collection>, lambda x: x)
```

```python
>>> from functools import reduce
>>> def add(x, y):
...     return x + y
...
>>> def mul(x, y):
...     return x * y
...
>>> def sub(x, y):
...     return x - y
...
>>> compose = reduce(lambda f, g: lambda x: f(g(x)), [add, mul, sub], lambda x: x)
>>> compose(1, 2)
-3
```

**[🔼Back to Top](#table-of-contents)**

## Currying

**Returns a function that takes one argument and returns another function that takes the next argument, and so on.**

```python
<func> = lambda <arg_1>: lambda <arg_2>: …    # Returns a function object.
```

```python
>>> def add(x, y):
...     return x + y
...
>>> add_1 = lambda x: add(x, 1)
>>> add_1(2)
3
```

**[🔼Back to Top](#table-of-contents)**

## Memoize

**Returns a function that caches the return value for each argument.**

```python
from functools import lru_cache
<func> = lru_cache(maxsize=128, typed=False)(<func>)
```

```python
>>> from functools import lru_cache
>>> @lru_cache(maxsize=128, typed=False)
... def fib(n):
...     if n < 2:
...         return n
...     return fib(n - 1) + fib(n - 2)
...
>>> fib(10)
55
```

**[🔼Back to Top](#table-of-contents)**

## Decorator

**A function that takes another function and extends the behavior of the latter function without explicitly modifying it.**

```python
@<decorator>
def <func>(…):
    pass
```

```python
>>> def decorator(func):
...     def wrapper(*args, **kwargs):
...         print('Before')
...         func(*args, **kwargs)
...         print('After')
...     return wrapper
...

>>> @decorator
... def func():
...     print('Inside')
...
>>> func()
Before
Inside
After
```

**[🔼Back to Top](#table-of-contents)**

## Closure

**A function that remembers the values from the enclosing lexical scope even when the program flow is no longer in that scope.**

```python
def <func>(…):
    <var> = <val>
    def <inner_func>(…):
        pass
    return <inner_func>
```

```python
>>> def func():
...     x = 1

...     def inner_func():
...         print(x)
...
>>> inner_func = func()
>>> inner_func()
1
```

**[🔼Back to Top](#table-of-contents)**

## Generator

**A function that returns an iterator object.**

```python
def <func>(…):
    yield <val>
```

```python
>>> def func():
...     yield 1
...     yield 2
...     yield 3
...
>>> list(func())
[1, 2, 3]
```

**[🔼Back to Top](#table-of-contents)**

## Generator

**A function that returns an iterator object.**

```python
def <func>(…):
    yield <val>
```

```python
>>> def func():
...     yield 1
...     yield 2
...     yield 3
...
>>> list(func())
[1, 2, 3]
```

**[🔼Back to Top](#table-of-contents)**

## Iterator

**An object that represents a stream of data.**

```python
<iter> = iter(<collection>)                   # Returns an iterator object.

<el> = next(<iter>)                           # Returns the next element.
```

```python
>>> iter = iter([1, 2, 3])
>>> next(iter)
1
>>> next(iter)
2
>>> next(iter)
3
```


**[🔼Back to Top](#table-of-contents)**

## Context Manager

**A class that defines the runtime context to be established when executing a with statement.**

```python
class <context_manager>:
    def __enter__(self):
        pass

    def __exit__(self, exc_type, exc_value, traceback):
        pass
```

```python
>>> class context_manager:
...     def __enter__(self):
...         print('Enter')
...
...     def __exit__(self, exc_type, exc_value, traceback):
...         print('Exit')
...
>>> with context_manager():
...     print('Inside')
...
Enter
Inside
Exit
```

**[🔼Back to Top](#table-of-contents)**

## Decorator

**A function that takes another function and extends the behavior of the latter function without explicitly modifying it.**

```python
@<decorator>
def <func>(…):
    pass
```

```python
>>> def decorator(func):
...     def wrapper(*args, **kwargs):
...         print('Before')
...         func(*args, **kwargs)
...         print('After')
...     return wrapper
...

>>> @decorator
... def func():
...     print('Inside')
...
>>> func()
Before
Inside
After
```

**[🔼Back to Top](#table-of-contents)**

# Modules

## Argparse

**A module that makes it easy to write user-friendly command-line interfaces.**

```python
import argparse

parser = argparse.ArgumentParser(description='<description>')
parser.add_argument('<arg>', type=<type>, help='<help>')
parser.add_argument('<arg>', type=<type>, help='<help>')
parser.add_argument('<arg>', type=<type>, help='<help>')
args = parser.parse_args()
```

```python
>>> import argparse
>>> parser = argparse.ArgumentParser(description='A sample program')
>>> parser.add_argument('x', type=int, help='The base')
>>> parser.add_argument('y', type=int, help='The exponent')
>>> parser.add_argument('-v', '--verbose', action='store_true', help='Increase output verbosity')
>>> args = parser.parse_args()
>>> args.x ** args.y
1000
```

**[🔼Back to Top](#table-of-contents)**

## Logging

**A module that provides a set of convenience functions for simple logging usage.**

```python
import logging

logging.basicConfig(level=logging.<level>, format='%(asctime)s %(message)s')
logging.<level>(<msg>)
```

```python
>>> import logging
>>> logging.basicConfig(level=logging.DEBUG, format='%(asctime)s %(message)s')
>>> logging.debug('This is a debug message')
2019-01-01 00:00:00,000 This is a debug message
```

**[🔼Back to Top](#table-of-contents)**

## Sqlite

**A module that provides a SQL interface compliant with the DB-API 2.0 specification.**

```python
import sqlite3

conn = sqlite3.connect('<db>')
c = conn.cursor()
c.execute('CREATE TABLE <table> (<col1> <type>, <col2> <type>, <col3> <type>)')
c.execute('INSERT INTO <table> VALUES (<val1>, <val2>, <val3>)')
conn.commit()
c.execute('SELECT * FROM <table>')
c.fetchall()
```

```python
>>> import sqlite3
>>> conn = sqlite3.connect('test.db')
>>> c = conn.cursor()
>>> c.execute('CREATE TABLE test (col1 int, col2 str, col3 float)')
<sqlite3.Cursor object at 0x7f8b0c0b0c00>
>>> c.execute('INSERT INTO test VALUES (1, "a", 1.0)')
<sqlite3.Cursor object at 0x7f8b0c0b0c00>
>>> conn.commit()
>>> c.execute('SELECT * FROM test')
<sqlite3.Cursor object at 0x7f8b0c0b0c00>
>>> c.fetchall()
[(1, 'a', 1.0)]
```

**[🔼Back to Top](#table-of-contents)**

## Pickle

**A module that implements binary protocols for serializing and de-serializing a Python object structure.**

```python
import pickle

with open('<file>', 'wb') as f:
    pickle.dump(<obj>, f)

with open('<file>', 'rb') as f:
    pickle.load(f)
```

```python
>>> import pickle
>>> with open('test.pkl', 'wb') as f:
...     pickle.dump([1, 2, 3], f)
...
>>> with open('test.pkl', 'rb') as f:
...     pickle.load(f)
...
[1, 2, 3]
```

**[🔼Back to Top](#table-of-contents)**

## Collections

**A module that implements specialized container datatypes providing alternatives to Python’s general purpose built-in containers, dict, list, set, and tuple.**

```python
from collections import <collection>

<collection>(<iterable>)
```

```python
>>> from collections import Counter
>>> Counter([1, 2, 3, 1, 2, 3, 1, 2, 3])
Counter({1: 3, 2: 3, 3: 3})
```

**[🔼Back to Top](#table-of-contents)**

## Counter

**A dict subclass for counting hashable objects.**

```python
from collections import Counter

Counter(<iterable>)
```

```python
>>> from collections import Counter
>>> Counter([1, 2, 3, 1, 2, 3, 1, 2, 3])
Counter({1: 3, 2: 3, 3: 3})
```

**[🔼Back to Top](#table-of-contents)**

## OrderedDict

**A dict subclass that remembers the order entries were added.**

```python
from collections import OrderedDict

OrderedDict(<iterable>)
```

```python
>>> from collections import OrderedDict
>>> OrderedDict([('a', 1), ('b', 2), ('c', 3)])
OrderedDict([('a', 1), ('b', 2), ('c', 3)])
```

**[🔼Back to Top](#table-of-contents)**

## Defaultdict

**A dict subclass that calls a factory function to supply missing values.**

```python
from collections import defaultdict

defaultdict(<factory_function>, <iterable>)
```

```python
>>> from collections import defaultdict

>>> def default_factory():
...     return 'default value'

>>> d = defaultdict(default_factory, foo='bar')

>>> print('d[foo]:', d['foo'])
d[foo]: bar

>>> print('d[bar]:', d['bar'])
d[bar]: default value
```

**[🔼Back to Top](#table-of-contents)**

## Namedtuple

**A factory function for creating tuple subclasses with named fields.**

```python
from collections import namedtuple

namedtuple('<name>', '<fields>')
```

```python
>>> from collections import namedtuple

>>> Point = namedtuple('Point', ['x', 'y'])

>>> p = Point(11, y=22)     # instantiate with positional or keyword arguments

>>> p[0] + p[1]             # indexable like the plain tuple (11, 22)

33

>>> x, y = p                # unpack like a regular tuple

>>> x, y

(11, 22)

>>> p.x + p.y               # fields also accessible by name

33

>>> p                       # readable __repr__ with a name=value style

Point(x=11, y=22)

>>> d = p._asdict()         # convert to a dictionary

>>> d['x']

11

>>> Point(**d)              # convert from a dictionary

Point(x=11, y=22)

>>> p._replace(x=100)       # _replace() is like str.replace() but targets named fields

Point(x=100, y=22)
```

**[🔼Back to Top](#table-of-contents)**

## ChainMap

**A dict-like class for creating a single view of multiple mappings.**

```python

from collections import ChainMap

ChainMap(<dict1>, <dict2>, ...)
```

```python
>>> from collections import ChainMap

>>> a = {'x': 1, 'z': 3}
>>> b = {'y': 2, 'z': 4}

>>> c = ChainMap(a, b)

>>> c['x']       # Notice how values from a are used, not b

1

>>> c['y']       # Notice how values from b are used, not a

2

>>> c['z']       # Notice how the first occurrence of z is used

3

>>> del c['z']   # Deleting a value only affects the first mapping

>>> a['z']       # a['z'] is now gone

3

>>> b['z']       # b['z'] is still there

4

>>> len(c)       # len() counts the number of mappings, not elements

3

>>> list(c.keys())   # Notice how z is no longer there

['y', 'x']

>>> list(c.values()) # Notice how z is no longer there

[2, 1]
```

**[🔼Back to Top](#table-of-contents)**

## Heapq

**A module for implementing heaps based on regular lists.**

```python

import heapq

heapq.<function>(<list>, <value>)
```

```python
>>> import heapq

>>> h = []

>>> heapq.heappush(h, (5, 'write code'))

>>> heapq.heappush(h, (7, 'release product'))

>>> heapq.heappush(h, (1, 'write spec'))

>>> heapq.heappush(h, (3, 'create tests'))

>>> heapq.heappop(h)

(1, 'write spec')

>>> heapq.heappop(h)

(3, 'create tests')

>>> heapq.heappop(h)

(5, 'write code')

>>> heapq.heappop(h)

(7, 'release product')
```

**[🔼Back to Top](#table-of-contents)**

## Bisect

**A module for maintaining a list in sorted order without having to sort the list after each insertion.**

```python

import bisect

bisect.<function>(<list>, <value>)
```

```python
>>> import bisect

>>> scores = []

>>> bisect.insort(scores, 33)

>>> bisect.insort(scores, 99)

>>> bisect.insort(scores, 77)

>>> bisect.insort(scores, 70)

>>> bisect.insort(scores, 89)

>>> bisect.insort(scores, 90)

>>> bisect.insort(scores, 100)

>>> scores

[33, 70, 77, 89, 90, 99, 100]
```

**[🔼Back to Top](#table-of-contents)**

## Array

**An array is a container that holds a fixed number of items of a single type.**

```python

from array import array

array('<typecode>', <iterable>)
```

```python
>>> from array import array

>>> a = array('H', [4000, 10, 700, 22222])

>>> sum(a)

26932

>>> a[1:3]

array('H', [10, 700])
```

**[🔼Back to Top](#table-of-contents)**

## Weakref

**A module for weak references.**

```python

import weakref

weakref.<function>(<object>)
```

```python
>>> import weakref

>>> a_set = {0, 1}

>>> wref = weakref.ref(a_set)

>>> wref

<weakref at 0x7f9b7c2d8e18; to 'set' at 0x7f9b7c2d8e48>

>>> wref()

{0, 1}

>>> a_set = {2, 3, 4}

>>> wref()

>>> wref() is None

True
```

**[🔼Back to Top](#table-of-contents)**

## Types

**A module that provides access to the internal type system.**

```python

import types

types.<function>(<object>)
```

```python

>>> import types

>>> def double(x):

...     return x * 2

...

>>> type(double)

<class 'function'>

>>> type(abs)

<class 'builtin_function_or_method'>

>>> type(int)

<class 'type'>

>>> type(str)

<class 'type'>

>>> type(type)

<class 'type'>

>>> type(double) == types.FunctionType

True

>>> type(abs) == types.BuiltinFunctionType

True

>>> type(int) == types.TypeType

True

>>> type(str) == types.TypeType

True

>>> type(type) == types.TypeType

True
```

**[🔼Back to Top](#table-of-contents)**

## Copy

**A module for shallow and deep copying.**

```python

import copy

copy.<function>(<object>)
```

```python

>>> import copy

>>> l1 = [3, [55, 44], (7, 8, 9)]

>>> l2 = list(l1)

>>> l1

[3, [55, 44], (7, 8, 9)]


>>> l2

[3, [55, 44], (7, 8, 9)]

>>> l1.append(100)

>>> l1

[3, [55, 44], (7, 8, 9), 100]

>>> l2

[3, [55, 44], (7, 8, 9)]

>>> l1[1].remove(55)

>>> l1

[3, [44], (7, 8, 9), 100]

>>> l2

[3, [44], (7, 8, 9)]

>>> l2[1] += [33, 22]

>>> l2

[3, [44, 33, 22], (7, 8, 9)]

>>> l1

[3, [44], (7, 8, 9), 100]

>>> l1[2] += (10, 11)

>>> l1

[3, [44], (7, 8, 9, 10, 11), 100]

>>> l2

[3, [44, 33, 22], (7, 8, 9)]

>>> l3 = copy.copy(l1)

>>> l3

[3, [44], (7, 8, 9, 10, 11), 100]   

>>> l1.append(100)

>>> l1

[3, [44], (7, 8, 9, 10, 11), 100, 100]

>>> l3

[3, [44], (7, 8, 9, 10, 11), 100]

>>> l1[1].remove(44)

>>> l1

[3, [], (7, 8, 9, 10, 11), 100, 100]

>>> l3

[3, [], (7, 8, 9, 10, 11), 100]

>>> l3[2] += (10, 11)

>>> l3

[3, [], (7, 8, 9, 10, 11, 10, 11), 100]

>>> l1

[3, [], (7, 8, 9, 10, 11), 100, 100]

>>> l1 = [3, [55, 44], (7, 8, 9)]

>>> l2 = copy.deepcopy(l1)

>>> l1

[3, [55, 44], (7, 8, 9)]

>>> l2

[3, [55, 44], (7, 8, 9)]

>>> l1.append(100)

>>> l1

[3, [55, 44], (7, 8, 9), 100]

>>> l2

[3, [55, 44], (7, 8, 9)]

>>> l1[1].remove(55)

>>> l1

[3, [44], (7, 8, 9), 100]

>>> l2

[3, [55, 44], (7, 8, 9)]

>>> l2[1] += [33, 22]

>>> l2

[3, [55, 44, 33, 22], (7, 8, 9)]

>>> l1

[3, [44], (7, 8, 9), 100]

>>> l1[2] += (10, 11)

>>> l1

[3, [44], (7, 8, 9, 10, 11), 100]

>>> l2

[3, [55, 44, 33, 22], (7, 8, 9)]
```

**[🔼Back to Top](#table-of-contents)**

## Pprint

**A module that provides a capability to “pretty-print” arbitrary Python data structures in a form which can be used as input to the interpreter.**

```python

import pprint

pprint.<function>(<object>)
```

```python

>>> import pprint

>>> t = [[[['black', 'cyan'], 'white', ['green', 'red']], [['magenta', 'yellow'], 'blue']]]

>>> pprint.pprint(t, width=30)

[[[['black', 'cyan'],

'white',

['green', 'red']],

[['magenta', 'yellow'],

'blue']]]

>>> pprint.pprint(t, width=30, depth=1)

[[['black', 'cyan'],

'white',

['green', 'red']],

[['magenta', 'yellow'],

'blue']]

>>> pprint.pprint(t, width=30, depth=2)

[[['black', 'cyan'],

'white',

['green', 'red']],

[['magenta', 'yellow'],

'blue']]

>>> pprint.pprint(t, width=30, depth=3)

[[['black', 'cyan'],

'white',

['green', 'red']],

[['magenta', 'yellow'],

'blue']]


>>> pprint.pprint(t, width=30, depth=4)

[[['black', 'cyan'],

'white',

['green', 'red']],

[['magenta', 'yellow'],

'blue']]

```

**[🔼Back to Top](#table-of-contents)**

## Reprlib

**A module that provides a version of repr() which can be used to produce abbreviated, recursive representations of large or deeply nested containers.**

```python

import reprlib

reprlib.<function>(<object>)
```

```python

>>> import reprlib

>>> reprlib.repr(set('supercalifragilisticexpialidocious'))


"{'a', 'c', 'd', 'e', 'f', 'g', 'i', 'l', 'o', 'p', 'r', 's', 't', 'u', 'x'}"

>>> t = [[[['black', 'cyan'], 'white', ['green', 'red']], [['magenta', 'yellow'], 'blue']]]

>>> reprlib.repr(t)

"[[[['black', 'cyan'], 'white', ['green', 'red']], [['magenta', 'yellow'], 'blue']]]"

>>> reprlib.repr(t, maxlevel=1)

"[[['black', 'cyan'], 'white', ['green', 'red']], [['magenta', 'yellow'], 'blue']]"

>>> reprlib.repr(t, maxlevel=2)

"[[['black', 'cyan'], 'white', ['green', 'red']], [['magenta', 'yellow'], 'blue']]"

>>> reprlib.repr(t, maxlevel=3)

"[[['black', 'cyan'], 'white', ['green', 'red']], [['magenta', 'yellow'], 'blue']]"

```

**[🔼Back to Top](#table-of-contents)**

## Enum

**A module that provides support for enumerations.**

```python

import enum

enum.<function>(<object>)
```

```python

>>> import enum

>>> class Color(enum.Enum):

...     RED = 1

...     GREEN = 2

...     BLUE = 3

...

>>> Color.RED

<Color.RED: 1>

>>> Color(1)

<Color.RED: 1>

>>> Color['RED']

<Color.RED: 1>

>>> Color.RED.name

'RED'

>>> Color.RED.value

1

>>> Color.RED == 1

False

>>> Color.RED == Color(1)

True

```

**[🔼Back to Top](#table-of-contents)**

## Pathlib

**A module that provides classes representing filesystem paths with semantics appropriate for different operating systems.**

```python

import pathlib

pathlib.<function>(<object>)
```

```python

>>> import pathlib

>>> p = pathlib.Path('.')

>>> p

PosixPath('.')

>>> p.absolute()

PosixPath('/home/username/Python')

>>> p.cwd()

PosixPath('/home/username/Python')

>>> p.home()

PosixPath('/home/username')
```

**[🔼Back to Top](#table-of-contents)**

## Functools

**A module that provides higher-order functions and operations on callable objects.**

```python

import functools

functools.<function>(<object>)
```

```python

>>> import functools

>>> def add(a, b):
...     return a + b

...

>>> add(1, 2)

3

>>> add = functools.partial(add, 1)

>>> add(2)

3
```

**[🔼Back to Top](#table-of-contents)**

## Itertools

**A module that provides functions creating iterators for efficient looping.**

```python

import itertools

itertools.<function>(<object>)
```

```python

>>> import itertools

>>> for i in itertools.count(1, 0.5):
...     print(i)

1
1.5
2.0
2.5
3.0
3.5
4.0

```

**[🔼Back to Top](#table-of-contents)**

## Contextlib

**A module that provides utilities for with-statement contexts.**

```python

import contextlib

contextlib.<function>(<object>)
```

```python

>>> import contextlib
>>> @contextlib.contextmanager

... def make_context():
...     print('entering')
...     try:
...         yield {}
...     except RuntimeError as err:
...         print('ERROR:', err)
...     finally:
...         print('exiting')

...

>>> with make_context() as value:
...     print('inside with statement:', value)

entering
inside with statement: {}
exiting

>>> with make_context() as value:
...     raise RuntimeError('showing example of handling an error')

entering
exiting
ERROR: showing example of handling an error

```

**[🔼Back to Top](#table-of-contents)**

## Atexit

**A module that provides one function, register(), that is used to register cleanup functions to be executed when the interpreter exits normally or unconditionally.**

```python

import atexit

atexit.<function>(<object>)
```

```python

>>> import atexit

>>> def my_cleanup(name):
...     print('Cleaning up', name)
...    raise RuntimeError('oops')

...

>>> atexit.register(my_cleanup, 'first')

<function my_cleanup at 0x7f9b8c0b9d08>

>>> atexit.register(my_cleanup, 'second')

<function my_cleanup at 0x7f9b8c0b9d08>

```

**[🔼Back to Top](#table-of-contents)**

## Traceback

**A module that provides functions to extract, format and print stack traces of Python programs.**

```python

import traceback

traceback.<function>(<object>)
```

```python

>>> import traceback

>>> def f():
...     g()

...

>>> def g():
...     h()

...

>>> def h():
...     i()

...

>>> def i():
...     traceback.print_stack()

...

>>> f()

File "test.py", line 2, in f
    g()
File "test.py", line 5, in g
    h()
File "test.py", line 8, in h
    i() 
File "test.py", line 11, in i
    traceback.print_stack()

```

**[🔼Back to Top](#table-of-contents)**

## Sys

**A module that provides access to some objects used or maintained by the interpreter and to functions that interact strongly with the interpreter.**

```python

import sys

sys.<function>(<object>)
```

```python

>>> import sys

>>> sys.argv

['/usr/bin/python3', 'test.py']

>>> sys.exit()

>>> sys.exit(1)

>>> sys.exit(0)

>>> sys.exit('Error message')

>>> sys.exit(1, 'Error message')

>>> sys.exit(0, 'Error message')

>>> sys.exit(1, 2, 3)

>>> sys.exit(0, 2, 3)

>>> sys.exit('Error message', 2, 3)

```

**[🔼Back to Top](#table-of-contents)**

## Time

**A module that provides various time-related functions.**

```python

import time

time.<function>(<object>)
```

```python

>>> import time

>>> time.time()

1610000000.0

>>> time.localtime()

time.struct_time(tm_year=2021, tm_mon=1, tm_mday=1, tm_hour=0, tm_min=0, tm_sec=0, tm_wday=0, tm_yday=1, tm_isdst=0)

>>> time.strftime('%Y-%m-%d %H:%M:%S', time.localtime())

'2021-01-01 00:00:00'

>>> time.strftime('%Y-%m-%d %H:%M:%S', time.gmtime())

'2021-01-01 00:00:00'

```

**[🔼Back to Top](#table-of-contents)**

## Datetime

**A module that supplies classes for manipulating dates and times in both simple and complex ways.**

```python

import datetime

datetime.<function>(<object>)
```

```python

>>> import datetime

>>> datetime.datetime.now()

datetime.datetime(2021, 1, 1, 0, 0)

>>> datetime.datetime.now().strftime('%Y-%m-%d %H:%M:%S')

'2021-01-01 00:00:00'

>>> datetime.datetime.now().strftime('%Y-%m-%d %H:%M:%S.%f')

'2021-01-01 00:00:00.000000'

```

**[🔼Back to Top](#table-of-contents)**

## Calendar

**A module that provides general calendar related functions.**

```python

import calendar

calendar.<function>(<object>)
```

```python

>>> import calendar

>>> calendar.isleap(2020)

True

>>> calendar.isleap(2021)

False

>>> calendar.isleap(2022)

False

```

**[🔼Back to Top](#table-of-contents)**

## Random

**A module that implements pseudo-random number generators for various distributions.**

```python

import random

random.<function>(<object>)
```

```python

>>> import random

>>> random.random()

0.123456789

>>> random.randint(1, 10)

5

>>> random.randrange(1, 10)

5

>>> random.randrange(1, 10, 2)

5

>>> random.choice([1, 2, 3, 4, 5])

5

>>> random.choice('Hello World')

'W'

>>> random.choices([1, 2, 3, 4, 5], k=3)

[5, 5, 5]

>>> random.choices('Hello World', k=3)

['W', 'W', 'W']

>>> random.sample([1, 2, 3, 4, 5], k=3)

[5, 5, 5]

```

**[🔼Back to Top](#table-of-contents)**

## Statistics

**A module that provides functions for calculating mathematical statistics of numeric (Real-valued) data.**

```python

import statistics

statistics.<function>(<object>)
```

```python

>>> import statistics

>>> statistics.mean([1, 2, 3, 4, 5])

3.0

>>> statistics.median([1, 2, 3, 4, 5])

3.0

>>> statistics.median_low([1, 2, 3, 4, 5])

3

>>> statistics.median_high([1, 2, 3, 4, 5])

3

>>> statistics.median_grouped([1, 2, 3, 4, 5])

3.0

>>> statistics.mode([1, 2, 3, 4, 5])

1

```

**[🔼Back to Top](#table-of-contents)**

## Math

**A module that provides access to the mathematical functions defined by the C standard.**

```python

import math

math.<function>(<object>)
```

```python

>>> import math

>>> math.pi

3.141592653589793

>>> math.e

2.718281828459045

>>> math.sin(math.pi / 2)

1.0

>>> math.cos(math.pi / 2)

6.123233995736766e-17

```

**[🔼Back to Top](#table-of-contents)**

# Cmath

**A module that provides access to mathematical functions for complex numbers.**

```python

import cmath

cmath.<function>(<object>)
```

```python

>>> import cmath

>>> cmath.pi

3.141592653589793

>>> cmath.e

2.718281828459045

>>> cmath.sin(cmath.pi / 2)

1j

>>> cmath.cos(cmath.pi / 2)

6.123233995736766e-17j

```

**[🔼Back to Top](#table-of-contents)**




## Threading

- **CPython interpreter can only run a single thread at a time.**
- **That is why using multiple threads won't result in a faster execution, unless at least one of the threads contains an I/O operation.**

```python
from threading import Thread, RLock, Semaphore, Event, Barrier
from concurrent.futures import ThreadPoolExecutor
```

### Thread

```python
<Thread> = Thread(target=<function>)           # Use `args=<collection>` to set the arguments.
<Thread>.start()                               # Starts the thread.
<bool> = <Thread>.is_alive()                   # Checks if the thread has finished executing.
<Thread>.join()                                # Waits for the thread to finish.
```

- **Use `'kwargs=<dict>'` to pass keyword arguments to the function.**
- **Use `'daemon=True'`, or the program will not be able to exit while the thread is alive.**

### Lock

```python
<lock> = RLock()                               # Lock that can only be released by acquirer.
<lock>.acquire()                               # Waits for the lock to be available.
<lock>.release()                               # Makes the lock available again.
```

#### Or:

```python
with <lock>:                                   # Enters the block by calling acquire(),
    ...                                        # and exits it with release().
```

### Semaphore, Event, Barrier

```python
<Semaphore> = Semaphore(value=1)               # Lock that can be acquired by 'value' threads.
<Event>     = Event()                          # Method wait() blocks until set() is called.
<Barrier>   = Barrier(n_times)                 # Wait() blocks until it's called n_times.
```

### Thread Pool Executor

- **Object that manages thread execution.**
- **An object with the same interface called ProcessPoolExecutor provides true parallelism by running a separate interpreter in each process. All arguments must be [pickable](#pickle).**

```python
<Exec> = ThreadPoolExecutor(max_workers=None)  # Or: `with ThreadPoolExecutor() as <name>: …`
<Exec>.shutdown(wait=True)                     # Blocks until all threads finish executing.
```

```python
<iter> = <Exec>.map(<func>, <args_1>, ...)     # A multithreaded and non-lazy map().
<Futr> = <Exec>.submit(<func>, <arg_1>, ...)   # Starts a thread and returns its Future object.
<bool> = <Futr>.done()                         # Checks if the thread has finished executing.
<obj>  = <Futr>.result()                       # Waits for thread to finish and returns result.
```

### Queue

**A thread-safe FIFO queue. For LIFO queue use LifoQueue.**

```python
from queue import Queue
<Queue> = Queue(maxsize=0)
```

```python
<Queue>.put(<el>)                              # Blocks until queue stops being full.
<Queue>.put_nowait(<el>)                       # Raises queue.Full exception if full.
<el> = <Queue>.get()                           # Blocks until queue stops being empty.
<el> = <Queue>.get_nowait()                    # Raises queue.Empty exception if empty.
```

**[🔼Back to Top](#table-of-contents)**

## Operator

**Module of functions that provide the functionality of operators.**

```python
import operator as op
<el>      = op.add/sub/mul/truediv/floordiv/mod(<el>, <el>)  # +, -, *, /, //, %
<int/set> = op.and_/or_/xor(<int/set>, <int/set>)            # &, |, ^
<bool>    = op.eq/ne/lt/le/gt/ge(<sortable>, <sortable>)     # ==, !=, <, <=, >, >=
<func>    = op.itemgetter/attrgetter/methodcaller(<obj>)     # [index/key], .name, .name()
```

```python
elementwise_sum  = map(op.add, list_a, list_b)
sorted_by_second = sorted(<collection>, key=op.itemgetter(1))
sorted_by_both   = sorted(<collection>, key=op.itemgetter(1, 0))
product_of_elems = functools.reduce(op.mul, <collection>)
union_of_sets    = functools.reduce(op.or_, <coll_of_sets>)
first_element    = op.methodcaller('pop', 0)(<list>)
```

- **Binary operators require objects to have and(), or(), xor() and invert() special methods, unlike logical operators that work on all types of objects.**
- **Also: `'<bool> = <bool> &|^ <bool>'` and `'<int> = <bool> &|^ <int>'`.**

**[🔼Back to Top](#table-of-contents)**

## Introspection

**Inspecting code at runtime.**

### Variables

```python
<list> = dir()                             # Names of local variables (incl. functions).
<dict> = vars()                            # Dict of local variables. Also locals().
<dict> = globals()                         # Dict of global variables.
```

### Attributes

```python
<list> = dir(<object>)                     # Names of object's attributes (incl. methods).
<dict> = vars(<object>)                    # Dict of writable attributes. Also <obj>.__dict__.
<bool> = hasattr(<object>, '<attr_name>')  # Checks if getattr() raises an AttributeError.
value  = getattr(<object>, '<attr_name>')  # Raises AttributeError if attribute is missing.
setattr(<object>, '<attr_name>', value)    # Only works on objects with '__dict__' attribute.
delattr(<object>, '<attr_name>')           # Same. Also `del <object>.<attr_name>`.
```

### Parameters

```python
<Sig>  = inspect.signature(<function>)     # Function's Signature object.
<dict> = <Sig>.parameters                  # Dict of Parameter objects.
<memb> = <Param>.kind                      # Member of ParameterKind enum.
<obj>  = <Param>.default                   # Default value or <Param>.empty.
<type> = <Param>.annotation                # Type or <Param>.empty.
```

**[🔼Back to Top](#table-of-contents)**

## Metaprogramming

**Code that generates code.**

### Type

**Type is the root class. If only passed an object it returns its type (class). Otherwise it creates a new class.**

```python
<class> = type('<class_name>', <tuple_of_parents>, <dict_of_class_attributes>)
```

```python
>>> Z = type('Z', (), {'a': 'abcde', 'b': 12345})
>>> z = Z()
```

### Meta Class

**A class that creates classes.**

```python
def my_meta_class(name, parents, attrs):
    attrs['a'] = 'abcde'
    return type(name, parents, attrs)
```

#### Or:

```python
class MyMetaClass(type):
    def __new__(cls, name, parents, attrs):
        attrs['a'] = 'abcde'
        return type.__new__(cls, name, parents, attrs)
```

- **New() is a class method that gets called before init(). If it returns an instance of its class, then that instance gets passed to init() as a 'self' argument.**
- **It receives the same arguments as init(), except for the first one that specifies the desired type of the returned instance (MyMetaClass in our case).**
- **Like in our case, new() can also be called directly, usually from a new() method of a child class (**`def __new__(cls): return super().__new__(cls)`**).**
- **The only difference between the examples above is that my_meta_class() returns a class of type type, while MyMetaClass() returns a class of type MyMetaClass.**

### Metaclass Attribute

**Right before a class is created it checks if it has the 'metaclass' attribute defined. If not, it recursively checks if any of his parents has it defined and eventually comes to type().**

```python
class MyClass(metaclass=MyMetaClass):
    b = 12345
```

```python
>>> MyClass.a, MyClass.b
('abcde', 12345)
```

### Type Diagram

```python
type(MyClass) == MyMetaClass         # MyClass is an instance of MyMetaClass.
type(MyMetaClass) == type            # MyMetaClass is an instance of type.
```

```text
+-------------+-------------+
|   Classes   | Metaclasses |
+-------------+-------------|
|   MyClass --> MyMetaClass |
|             |     v       |
|    object -----> type <+  |
|             |     ^ +--+  |
|     str ----------+       |
+-------------+-------------+
```

### Inheritance Diagram

```python
MyClass.__base__ == object           # MyClass is a subclass of object.
MyMetaClass.__base__ == type         # MyMetaClass is a subclass of type.
```

```text
+-------------+-------------+
|   Classes   | Metaclasses |
+-------------+-------------|
|   MyClass   | MyMetaClass |
|      v      |     v       |
|    object <----- type     |
|      ^      |             |
|     str     |             |
+-------------+-------------+
```

**[🔼Back to Top](#table-of-contents)**

## Eval

```python
>>> from ast import literal_eval
>>> literal_eval('[1, 2, 3]')
[1, 2, 3]
>>> literal_eval('1 + 2')
ValueError: malformed node or string
```

**[🔼Back to Top](#table-of-contents)**

## Coroutines

- **Coroutines have a lot in common with threads, but unlike threads, they only give up control when they call another coroutine and they don’t use as much memory.**
- **Coroutine definition starts with `'async'` and its call with `'await'`.**
- **`'asyncio.run(<coroutine>)'` is the main entry point for asynchronous programs.**
- **Functions wait(), gather() and as_completed() start multiple coroutines at the same time.**
- **Asyncio module also provides its own [Queue](#queue), [Event](#semaphore-event-barrier), [Lock](#lock) and [Semaphore](#semaphore-event-barrier) classes.**

#### Runs a terminal game where you control an asterisk that must avoid numbers:

```python
import asyncio, collections, curses, curses.textpad, enum, random

P = collections.namedtuple('P', 'x y')         # Position
D = enum.Enum('D', 'n e s w')                  # Direction
W, H = 15, 7                                   # Width, Height

def main(screen):
    curses.curs_set(0)                         # Makes cursor invisible.
    screen.nodelay(True)                       # Makes getch() non-blocking.
    asyncio.run(main_coroutine(screen))        # Starts running asyncio code.

async def main_coroutine(screen):
    moves = asyncio.Queue()
    state = {'*': P(0, 0), **{id_: P(W//2, H//2) for id_ in range(10)}}
    ai    = [random_controller(id_, moves) for id_ in range(10)]
    mvc   = [human_controller(screen, moves), model(moves, state), view(state, screen)]
    tasks = [asyncio.create_task(cor) for cor in ai + mvc]
    await asyncio.wait(tasks, return_when=asyncio.FIRST_COMPLETED)

async def random_controller(id_, moves):
    while True:
        d = random.choice(list(D))
        moves.put_nowait((id_, d))
        await asyncio.sleep(random.triangular(0.01, 0.65))

async def human_controller(screen, moves):
    while True:
        ch = screen.getch()
        key_mappings = {258: D.s, 259: D.n, 260: D.w, 261: D.e}
        if ch in key_mappings:
            moves.put_nowait(('*', key_mappings[ch]))
        await asyncio.sleep(0.005)

async def model(moves, state):
    while state['*'] not in (state[id_] for id_ in range(10)):
        id_, d = await moves.get()
        x, y   = state[id_]
        deltas = {D.n: P(0, -1), D.e: P(1, 0), D.s: P(0, 1), D.w: P(-1, 0)}
        state[id_] = P((x + deltas[d].x) % W, (y + deltas[d].y) % H)

async def view(state, screen):
    offset = P(curses.COLS//2 - W//2, curses.LINES//2 - H//2)
    while True:
        screen.erase()
        curses.textpad.rectangle(screen, offset.y-1, offset.x-1, offset.y+H, offset.x+W)
        for id_, p in state.items():
            screen.addstr(offset.y + (p.y - state['*'].y + H//2) % H,
                          offset.x + (p.x - state['*'].x + W//2) % W, str(id_))
        await asyncio.sleep(0.005)

if __name__ == '__main__':
    curses.wrapper(main)
```

<br>

**[🔼Back to Top](#table-of-contents)**

# Libraries

## Progress Bar

```python
# $ pip3 install tqdm
>>> from tqdm import tqdm
>>> from time import sleep
>>> for el in tqdm([1, 2, 3], desc='Processing'):
...     sleep(1)
Processing: 100%|████████████████████| 3/3 [00:03<00:00,  1.00s/it]
```

**[🔼Back to Top](#table-of-contents)**

## Plot

```python
# $ pip3 install matplotlib
import matplotlib.pyplot as plt
plt.plot(<x_data>, <y_data> [, label=<str>])   # Or: plt.plot(<y_data>)
plt.legend()                                   # Adds a legend.
plt.savefig(<path>)                            # Saves the figure.
plt.show()                                     # Displays the figure.
plt.clf()                                      # Clears the figure.
```

**[🔼Back to Top](#table-of-contents)**

## Table

#### Prints a CSV file as an ASCII table:

```python
# $ pip3 install tabulate
import csv, tabulate
with open('test.csv', encoding='utf-8', newline='') as file:
    rows   = csv.reader(file)
    header = next(rows)
    table  = tabulate.tabulate(rows, header)
print(table)
```

**[🔼Back to Top](#table-of-contents)**

## Curses

#### Runs a basic file explorer in the terminal:

```python
import curses, curses.ascii, os
from curses import A_REVERSE, KEY_DOWN, KEY_UP, KEY_LEFT, KEY_RIGHT, KEY_ENTER

def main(screen):
    ch, first, selected, paths = 0, 0, 0, os.listdir()
    while ch != curses.ascii.ESC:
        height, _ = screen.getmaxyx()
        screen.erase()
        for y, filename in enumerate(paths[first : first+height]):
            screen.addstr(y, 0, filename, A_REVERSE * (selected == first + y))
        ch = screen.getch()
        selected += (ch == KEY_DOWN) - (ch == KEY_UP)
        selected = max(0, min(len(paths)-1, selected))
        first += (first <= selected - height) - (first > selected)
        if ch in [KEY_LEFT, KEY_RIGHT, KEY_ENTER, 10, 13]:
            new_dir = '..' if ch == KEY_LEFT else paths[selected]
            if os.path.isdir(new_dir):
                os.chdir(new_dir)
                first, selected, paths = 0, 0, os.listdir()

if __name__ == '__main__':
    curses.wrapper(main)
```

**[🔼Back to Top](#table-of-contents)**

## Logging

```python
# $ pip3 install loguru
from loguru import logger
```

```python
logger.add('debug_{time}.log', colorize=True)  # Connects a log file.
logger.add('error_{time}.log', level='ERROR')  # Another file for errors or higher.
logger.<level>('A logging message.')           # Logs to file/s and prints to stderr.
```

- **Levels: `'debug'`, `'info'`, `'success'`, `'warning'`, `'error'`, `'critical'`.**

### Exceptions

**Exception description, stack trace and values of variables are appended automatically.**

```python
try:
    ...
except <exception>:
    logger.exception('An error happened.')
```

### Rotation

**Argument that sets a condition when a new log file is created.**

```python
rotation=<int>|<datetime.timedelta>|<datetime.time>|<str>
```

- **`'<int>'` - Max file size in bytes.**
- **`'<timedelta>'` - Max age of a file.**
- **`'<time>'` - Time of day.**
- **`'<str>'` - Any of above as a string: `'100 MB'`, `'1 month'`, `'monday at 12:00'`, ...**

### Retention

**Sets a condition which old log files get deleted.**

```python
retention=<int>|<datetime.timedelta>|<str>
```

- **`'<int>'` - Max number of files.**
- **`'<timedelta>'` - Max age of a file.**
- **`'<str>'` - Max age as a string: `'1 week, 3 days'`, `'2 months'`, ...**

**[🔼Back to Top](#table-of-contents)**

## Scraping

#### Scrapes Python's URL, version number and logo from its Wikipedia page:

```python
# $ pip3 install requests beautifulsoup4
import requests, bs4, os, sys

WIKI_URL = 'https://en.wikipedia.org/wiki/Python_(programming_language)'
try:
    html       = requests.get(WIKI_URL).text
    document   = bs4.BeautifulSoup(html, 'html.parser')
    table      = document.find('table', class_='infobox vevent')
    python_url = table.find('th', text='Website').next_sibling.a['href']
    version    = table.find('th', text='Stable release').next_sibling.strings.__next__()
    logo_url   = table.find('img')['src']
    logo       = requests.get(f'https:{logo_url}').content
    filename   = os.path.basename(logo_url)
    with open(filename, 'wb') as file:
        file.write(logo)
    print(f'{python_url}, {version}, file://{os.path.abspath(filename)}')
except requests.exceptions.ConnectionError:
    print("You've got problems with connection.", file=sys.stderr)
```

**[🔼Back to Top](#table-of-contents)**

## Web

```python
# $ pip3 install bottle
from bottle import run, route, static_file, template, post, request, response
import json
```

### Run

```python
run(host='localhost', port=8080)        # Runs locally.
run(host='0.0.0.0', port=80)            # Runs globally.
```

### Static Request

```python
@route('/img/<filename>')
def send_file(filename):
    return static_file(filename, root='img_dir/')
```

### Dynamic Request

```python
@route('/<sport>')
def send_html(sport):
    return template('<h1>{{title}}</h1>', title=sport)
```

### REST Request

```python
@post('/<sport>/odds')
def send_json(sport):
    team = request.forms.get('team')
    response.headers['Content-Type'] = 'application/json'
    response.headers['Cache-Control'] = 'no-cache'
    return json.dumps({'team': team, 'odds': [2.09, 3.74, 3.68]})
```

#### Test:

```python
# $ pip3 install requests
>>> import threading, requests
>>> threading.Thread(target=run, daemon=True).start()
>>> url = 'http://localhost:8080/football/odds'
>>> request_data = {'team': 'arsenal f.c.'}
>>> response = requests.post(url, data=request_data)
>>> response.json()
{'team': 'arsenal f.c.', 'odds': [2.09, 3.74, 3.68]}
```

**[🔼Back to Top](#table-of-contents)**

## Profiling

### Stopwatch

```python
from time import perf_counter
start_time = perf_counter()
...
duration_in_seconds = perf_counter() - start_time
```

### Timing a Snippet

```python
>>> from timeit import timeit
>>> timeit("''.join(str(i) for i in range(100))",
...        number=10000, globals=globals(), setup='pass')
0.34986
```

### Profiling by Line

```python
# $ pip3 install line_profiler memory_profiler
@profile
def main():
    a = [*range(10000)]
    b = {*range(10000)}
main()
```

```text
$ kernprof -lv test.py
Line #   Hits     Time  Per Hit   % Time  Line Contents
=======================================================
     1                                    @profile
     2                                    def main():
     3      1    955.0    955.0     43.7      a = [*range(10000)]
     4      1   1231.0   1231.0     56.3      b = {*range(10000)}
```

```text
$ python3 -m memory_profiler test.py
Line #         Mem usage      Increment   Line Contents
=======================================================
     1        37.668 MiB     37.668 MiB   @profile
     2                                    def main():
     3        38.012 MiB      0.344 MiB       a = [*range(10000)]
     4        38.477 MiB      0.465 MiB       b = {*range(10000)}
```

### Call Graph

#### Generates a PNG image of the call graph with highlighted bottlenecks:

```python
# $ pip3 install pycallgraph2; apt/brew install graphviz
import pycallgraph2 as cg, datetime

filename = f'profile-{datetime.datetime.now():%Y%m%d_%H%M%S}.png'
drawer = cg.output.GraphvizOutput(output_file=filename)
with cg.PyCallGraph(drawer):
    <code_to_be_profiled>
```

**[🔼Back to Top](#table-of-contents)**

## NumPy

**Array manipulation mini-language. It can run up to one hundred times faster than the equivalent Python code. An even faster alternative that runs on a GPU is called CuPy.**

```python
# $ pip3 install numpy
import numpy as np
```

```python
<array> = np.array(<list/list_of_lists>)                # Returns 1d/2d NumPy array.
<array> = np.zeros/ones(<shape>)                        # Also np.full(<shape>, <el>).
<array> = np.arange(from_inc, to_exc, ±step)            # Also np.linspace(start, stop, num).
<array> = np.random.randint(from_inc, to_exc, <shape>)  # Also np.random.random(<shape>).
```

```python
<view>  = <array>.reshape(<shape>)                      # Also `<array>.shape = <shape>`.
<array> = <array>.flatten()                             # Collapses array into one dimension.
<view>  = <array>.squeeze()                             # Removes dimensions of length one.
```

```python
<array> = <array>.sum/min/mean/var/std(axis)            # Passed dimension gets aggregated.
<array> = <array>.argmin(axis)                          # Returns indexes of smallest elements.
<array> = np.apply_along_axis(<func>, axis, <array>)    # Func can return a scalar or array.
```

- **Shape is a tuple of dimension sizes. A 100x50 RGB image has shape (50, 100, 3).**
- **Axis is an index of the dimension that gets aggregated. Leftmost dimension has index 0. Summing the RGB image along axis 2 will return a greyscale image with shape (50, 100).**
- **Passing a tuple of axes will chain the operations like this: `'<array>.<method>(axis_1, keepdims=True).<method>(axis_2).squeeze()'`.**

### Indexing

```bash
<el>       = <2d_array>[row_index, column_index]        # <3d_a>[table_i, row_i, column_i]
<1d_view>  = <2d_array>[row_index]                      # <3d_a>[table_i, row_i]
<1d_view>  = <2d_array>[:, column_index]                # <3d_a>[table_i, :, column_i]
```

```bash
<1d_array> = <2d_array>[row_indexes, column_indexes]    # <3d_a>[table_is, row_is, column_is]
<2d_array> = <2d_array>[row_indexes]                    # <3d_a>[table_is, row_is]
<2d_array> = <2d_array>[:, column_indexes]              # <3d_a>[table_is, :, column_is]
```

```bash
<2d_bools> = <2d_array> ><== <el>                       # <3d_array> ><== <1d_array>
<1d_array> = <2d_array>[<2d_bools>]                     # <3d_array>[<2d_bools>]
```

- **All examples also allow assignments.**

### Broadcasting

**Broadcasting is a set of rules by which NumPy functions operate on arrays of different sizes and/or dimensions.**

```python
left  = [[0.1], [0.6], [0.8]]                           # Shape: (3, 1)
right = [ 0.1 ,  0.6 ,  0.8 ]                           # Shape: (3,)
```

#### 1. If array shapes differ in length, left-pad the shorter shape with ones:

```python
left  = [[0.1], [0.6], [0.8]]                           # Shape: (3, 1)
right = [[0.1 ,  0.6 ,  0.8]]                           # Shape: (1, 3) <- !
```

#### 2. If any dimensions differ in size, expand the ones that have size 1 by duplicating their elements:

```python
left  = [[0.1,  0.1,  0.1],                             # Shape: (3, 3) <- !
         [0.6,  0.6,  0.6],
         [0.8,  0.8,  0.8]]

right = [[0.1,  0.6,  0.8],                             # Shape: (3, 3) <- !
         [0.1,  0.6,  0.8],
         [0.1,  0.6,  0.8]]
```

#### 3. If neither non-matching dimension has size 1, raise an error.

### Example

#### For each point returns index of its nearest point (`[0.1, 0.6, 0.8] => [1, 2, 1]`):

```python
>>> points = np.array([0.1, 0.6, 0.8])
 [ 0.1,  0.6,  0.8]
>>> wrapped_points = points.reshape(3, 1)
[[ 0.1],
 [ 0.6],
 [ 0.8]]
>>> distances = wrapped_points - points
[[ 0. , -0.5, -0.7],
 [ 0.5,  0. , -0.2],
 [ 0.7,  0.2,  0. ]]
>>> distances = np.abs(distances)
[[ 0. ,  0.5,  0.7],
 [ 0.5,  0. ,  0.2],
 [ 0.7,  0.2,  0. ]]
>>> i = np.arange(3)
[0, 1, 2]
>>> distances[i, i] = np.inf
[[ inf,  0.5,  0.7],
 [ 0.5,  inf,  0.2],
 [ 0.7,  0.2,  inf]]
>>> distances.argmin(1)
[1, 2, 1]
```

**[🔼Back to Top](#table-of-contents)**

## Image

```python
# $ pip3 install pillow
from PIL import Image
```

```python
<Image> = Image.new('<mode>', (width, height))   # Also: `color=<int/tuple/str>`.
<Image> = Image.open(<path>)                     # Identifies format based on file contents.
<Image> = <Image>.convert('<mode>')              # Converts image to the new mode.
<Image>.save(<path>)                             # Selects format based on the path extension.
<Image>.show()                                   # Opens image in default preview app.
```

```python
<int/tuple> = <Image>.getpixel((x, y))           # Returns a pixel.
<Image>.putpixel((x, y), <int/tuple>)            # Writes a pixel to the image.
<ImagingCore> = <Image>.getdata()                # Returns a flattened sequence of pixels.
<Image>.putdata(<list/ImagingCore>)              # Writes a flattened sequence of pixels.
<Image>.paste(<Image>, (x, y))                   # Writes passed image to the image.
```

```bash
<2d_array> = np.array(<Image_L>)                 # Creates NumPy array from greyscale image.
<3d_array> = np.array(<Image_RGB/A>)             # Creates NumPy array from color image.
<Image>    = Image.fromarray(np.uint8(<array>))  # Use <array>.clip(0, 255) to clip the values.
```

### Modes

- **`'1'` - 1-bit pixels, black and white, stored with one pixel per byte.**
- **`'L'` - 8-bit pixels, greyscale.**
- **`'RGB'` - 3x8-bit pixels, true color.**
- **`'RGBA'` - 4x8-bit pixels, true color with transparency mask.**
- **`'HSV'` - 3x8-bit pixels, Hue, Saturation, Value color space.**

### Examples

#### Creates a PNG image of a rainbow gradient:

```python
WIDTH, HEIGHT = 100, 100
n_pixels = WIDTH * HEIGHT
hues = (255 * i/n_pixels for i in range(n_pixels))
img = Image.new('HSV', (WIDTH, HEIGHT))
img.putdata([(int(h), 255, 255) for h in hues])
img.convert('RGB').save('test.png')
```

#### Adds noise to a PNG image:

```python
from random import randint
add_noise = lambda value: max(0, min(255, value + randint(-20, 20)))
img = Image.open('test.png').convert('HSV')
img.putdata([(add_noise(h), s, v) for h, s, v in img.getdata()])
img.convert('RGB').save('test.png')
```

### Image Draw

```python
from PIL import ImageDraw
<ImageDraw> = ImageDraw.Draw(<Image>)
```

```python
<ImageDraw>.point((x, y))                        # Truncates floats into ints.
<ImageDraw>.line((x1, y1, x2, y2 [, ...]))       # To get anti-aliasing use Image's resize().
<ImageDraw>.arc((x1, y1, x2, y2), deg1, deg2)    # Always draws in clockwise direction.
<ImageDraw>.rectangle((x1, y1, x2, y2))          # To rotate use Image's rotate() and paste().
<ImageDraw>.polygon((x1, y1, x2, y2, ...))       # Last point gets connected to the first.
<ImageDraw>.ellipse((x1, y1, x2, y2))            # To rotate use Image's rotate() and paste().
```

- **Use `'fill=<color>'` to set the primary color.**
- **Use `'width=<int>'` to set the width of lines or contours.**
- **Use `'outline=<color>'` to set the color of the contours.**
- **Color can be an int, tuple, `'#rrggbb[aa]'` string or a color name.**

## Animation

#### Creates a GIF of a bouncing ball:

```python
# $ pip3 install imageio
from PIL import Image, ImageDraw
import imageio

WIDTH, HEIGHT, R = 126, 126, 10
frames = []
for velocity in range(1, 16):
    y = sum(range(velocity))
    frame = Image.new('L', (WIDTH, HEIGHT))
    draw  = ImageDraw.Draw(frame)
    draw.ellipse((WIDTH/2-R, y, WIDTH/2+R, y+R*2), fill='white')
    frames.append(frame)
frames += reversed(frames[1:-1])
imageio.mimsave('test.gif', frames, duration=0.03)
```

**[🔼Back to Top](#table-of-contents)**

## Audio

```python
import wave
```

```python
<Wave_read>  = wave.open('<path>', 'rb')        # Opens the WAV file.
framerate    = <Wave_read>.getframerate()       # Number of frames per second.
nchannels    = <Wave_read>.getnchannels()       # Number of samples per frame.
sampwidth    = <Wave_read>.getsampwidth()       # Sample size in bytes.
nframes      = <Wave_read>.getnframes()         # Number of frames.
<params>     = <Wave_read>.getparams()          # Immutable collection of above.
<bytes>      = <Wave_read>.readframes(nframes)  # Returns next 'nframes' frames.
```

```python
<Wave_write> = wave.open('<path>', 'wb')        # Truncates existing file.
<Wave_write>.setframerate(<int>)                # 44100 for CD, 48000 for video.
<Wave_write>.setnchannels(<int>)                # 1 for mono, 2 for stereo.
<Wave_write>.setsampwidth(<int>)                # 2 for CD quality sound.
<Wave_write>.setparams(<params>)                # Sets all parameters.
<Wave_write>.writeframes(<bytes>)               # Appends frames to the file.
```

- **Bytes object contains a sequence of frames, each consisting of one or more samples.**
- **In a stereo signal, the first sample of a frame belongs to the left channel.**
- **Each sample consists of one or more bytes that, when converted to an integer, indicate the displacement of a speaker membrane at a given moment.**
- **If sample width is one byte, then the integer should be encoded unsigned.**
- **For all other sizes, the integer should be encoded signed with little-endian byte order.**

### Sample Values

```text
+-----------+-----------+------+-----------+
| sampwidth |    min    | zero |    max    |
+-----------+-----------+------+-----------+
|     1     |         0 |  128 |       255 |
|     2     |    -32768 |    0 |     32767 |
|     3     |  -8388608 |    0 |   8388607 |
+-----------+-----------+------+-----------+
```

### Read Float Samples from WAV File

```python
def read_wav_file(filename):
    def get_int(bytes_obj):
        an_int = int.from_bytes(bytes_obj, 'little', signed=(sampwidth != 1))
        return an_int - 128 * (sampwidth == 1)
    with wave.open(filename, 'rb') as file:
        sampwidth = file.getsampwidth()
        frames = file.readframes(-1)
    bytes_samples = (frames[i : i+sampwidth] for i in range(0, len(frames), sampwidth))
    return [get_int(b) / pow(2, sampwidth * 8 - 1) for b in bytes_samples]
```

### Write Float Samples to WAV File

```python
def write_to_wav_file(filename, float_samples, nchannels=1, sampwidth=2, framerate=44100):
    def get_bytes(a_float):
        a_float = max(-1, min(1 - 2e-16, a_float))
        a_float += sampwidth == 1
        a_float *= pow(2, sampwidth * 8 - 1)
        return int(a_float).to_bytes(sampwidth, 'little', signed=(sampwidth != 1))
    with wave.open(filename, 'wb') as file:
        file.setnchannels(nchannels)
        file.setsampwidth(sampwidth)
        file.setframerate(framerate)
        file.writeframes(b''.join(get_bytes(f) for f in float_samples))
```

### Examples

#### Saves a 440 Hz sine wave to a mono WAV file:

```python
from math import pi, sin
samples_f = (sin(i * 2 * pi * 440 / 44100) for i in range(100000))
write_to_wav_file('test.wav', samples_f)
```

#### Adds noise to a mono WAV file:

```python
from random import random
add_noise = lambda value: value + (random() - 0.5) * 0.03
samples_f = (add_noise(f) for f in read_wav_file('test.wav'))
write_to_wav_file('test.wav', samples_f)
```

#### Plays a WAV file:

```python
# $ pip3 install simpleaudio
from simpleaudio import play_buffer
with wave.open('test.wav', 'rb') as file:
    p = file.getparams()
    frames = file.readframes(-1)
    play_buffer(frames, p.nchannels, p.sampwidth, p.framerate)
```

### Text to Speech

```python
# $ pip3 install pyttsx3
import pyttsx3
engine = pyttsx3.init()
engine.say('Sally sells seashells by the seashore.')
engine.runAndWait()
```

## Synthesizer

#### Plays Popcorn by Gershon Kingsley:

```python
# $ pip3 install simpleaudio
import itertools as it, math, struct, simpleaudio

F  = 44100
P1 = '71♩,69♪,,71♩,66♪,,62♩,66♪,,59♩,,'
P2 = '71♩,73♪,,74♩,73♪,,74♪,,71♪,,73♩,71♪,,73♪,,69♪,,71♩,69♪,,71♪,,67♪,,71♩,,'
get_pause   = lambda seconds: it.repeat(0, int(seconds * F))
sin_f       = lambda i, hz: math.sin(i * 2 * math.pi * hz / F)
get_wave    = lambda hz, seconds: (sin_f(i, hz) for i in range(int(seconds * F)))
get_hz      = lambda key: 8.176 * 2 ** (int(key) / 12)
parse_note  = lambda note: (get_hz(note[:2]), 1/4 if '♩' in note else 1/8)
get_samples = lambda note: get_wave(*parse_note(note)) if note else get_pause(1/8)
samples_f   = it.chain.from_iterable(get_samples(n) for n in f'{P1},{P1},{P2}'.split(','))
samples_b   = b''.join(struct.pack('<h', int(f * 30000)) for f in samples_f)
simpleaudio.play_buffer(samples_b, 1, 2, F)
```

**[🔼Back to Top](#table-of-contents)**

## Pygame

```python
# $ pip3 install pygame
import pygame as pg

pg.init()
screen = pg.display.set_mode((500, 500))
rect = pg.Rect(240, 240, 20, 20)
while all(event.type != pg.QUIT for event in pg.event.get()):
    deltas = {pg.K_UP: (0, -1), pg.K_RIGHT: (1, 0), pg.K_DOWN: (0, 1), pg.K_LEFT: (-1, 0)}
    for ch, is_pressed in enumerate(pg.key.get_pressed()):
        rect = rect.move(deltas[ch]) if ch in deltas and is_pressed else rect
    screen.fill((0, 0, 0))
    pg.draw.rect(screen, (255, 255, 255), rect)
    pg.display.flip()
```

### Rectangle

**Object for storing rectangular coordinates.**

```python
<Rect> = pg.Rect(x, y, width, height)           # Floats get truncated into ints.
<int>  = <Rect>.x/y/centerx/centery/…           # Top, right, bottom, left. Allows assignments.
<tup.> = <Rect>.topleft/center/…                # Topright, bottomright, bottomleft. Same.
<Rect> = <Rect>.move((x, y))                    # Use move_ip() to move in-place.
```

```python
<bool> = <Rect>.collidepoint((x, y))            # Checks if rectangle contains a point.
<bool> = <Rect>.colliderect(<Rect>)             # Checks if two rectangles overlap.
<int>  = <Rect>.collidelist(<list_of_Rect>)     # Returns index of first colliding Rect or -1.
<list> = <Rect>.collidelistall(<list_of_Rect>)  # Returns indexes of all colliding rectangles.
```

### Surface

**Object for representing images.**

```python
<Surf> = pg.display.set_mode((width, height))   # Returns a display surface.
<Surf> = pg.Surface((width, height))            # New RGB surface. RGBA if `flags=pg.SRCALPHA`.
<Surf> = pg.image.load('<path>')                # Loads the image. Format depends on source.
<Surf> = <Surf>.subsurface(<Rect>)              # Returns a subsurface.
```

```python
<Surf>.fill(color)                              # Tuple, Color('#rrggbb[aa]') or Color(<name>).
<Surf>.set_at((x, y), color)                    # Updates pixel.
<Surf>.blit(<Surf>, (x, y))                     # Draws passed surface to the surface.
```

```python
from pygame.transform import scale, ...
<Surf> = scale(<Surf>, (width, height))         # Returns scaled surface.
<Surf> = rotate(<Surf>, anticlock_degrees)      # Returns rotated and scaled surface.
<Surf> = flip(<Surf>, x_bool, y_bool)           # Returns flipped surface.
```

```python
from pygame.draw import line, ...
line(<Surf>, color, (x1, y1), (x2, y2), width)  # Draws a line to the surface.
arc(<Surf>, color, <Rect>, from_rad, to_rad)    # Also: ellipse(<Surf>, color, <Rect>, width=0)
rect(<Surf>, color, <Rect>, width=0)            # Also: polygon(<Surf>, color, points, width=0)
```

### Font

```python
<Font> = pg.font.SysFont('<name>', size)        # Loads the system font or default if missing.
<Font> = pg.font.Font('<path>', size)           # Loads the TTF file. Pass None for default.
<Surf> = <Font>.render(text, antialias, color)  # Background color can be specified at the end.
```

### Sound

```python
<Sound> = pg.mixer.Sound('<path>')              # Loads the WAV file.
<Sound>.play()                                  # Starts playing the sound.
```

### Basic Mario Brothers Example

```python
import collections, dataclasses, enum, io, itertools as it, pygame as pg, urllib.request
from random import randint

P = collections.namedtuple('P', 'x y')          # Position
D = enum.Enum('D', 'n e s w')                   # Direction
W, H, MAX_S = 50, 50, P(5, 10)                  # Width, Height, Max speed

def main():
    def get_screen():
        pg.init()
        return pg.display.set_mode((W*16, H*16))
    def get_images():
        url = 'https://gto76.github.io/python-cheatsheet/web/mario_bros.png'
        img = pg.image.load(io.BytesIO(urllib.request.urlopen(url).read()))
        return [img.subsurface(get_rect(x, 0)) for x in range(img.get_width() // 16)]
    def get_mario():
        Mario = dataclasses.make_dataclass('Mario', 'rect spd facing_left frame_cycle'.split())
        return Mario(get_rect(1, 1), P(0, 0), False, it.cycle(range(3)))
    def get_tiles():
        border = [(x, y) for x in range(W) for y in range(H) if x in [0, W-1] or y in [0, H-1]]
        platforms = [(randint(1, W-2), randint(2, H-2)) for _ in range(W*H // 10)]
        return [get_rect(x, y) for x, y in border + platforms]
    def get_rect(x, y):
        return pg.Rect(x*16, y*16, 16, 16)
    run(get_screen(), get_images(), get_mario(), get_tiles())

def run(screen, images, mario, tiles):
    clock = pg.time.Clock()
    while all(event.type != pg.QUIT for event in pg.event.get()):
        keys = {pg.K_UP: D.n, pg.K_RIGHT: D.e, pg.K_DOWN: D.s, pg.K_LEFT: D.w}
        pressed = {keys.get(ch) for ch, is_prsd in enumerate(pg.key.get_pressed()) if is_prsd}
        update_speed(mario, tiles, pressed)
        update_position(mario, tiles)
        draw(screen, images, mario, tiles, pressed)
        clock.tick(28)

def update_speed(mario, tiles, pressed):
    x, y = mario.spd
    x += 2 * ((D.e in pressed) - (D.w in pressed))
    x -= (x > 0) - (x < 0)
    y += 1 if D.s not in get_boundaries(mario.rect, tiles) else (D.n in pressed) * -10
    mario.spd = P(x=max(-MAX_S.x, min(MAX_S.x, x)), y=max(-MAX_S.y, min(MAX_S.y, y)))

def update_position(mario, tiles):
    x, y = mario.rect.topleft
    n_steps = max(abs(s) for s in mario.spd)
    for _ in range(n_steps):
        mario.spd = stop_on_collision(mario.spd, get_boundaries(mario.rect, tiles))
        x, y = x + mario.spd.x / n_steps, y + mario.spd.y / n_steps
        mario.rect.topleft = x, y

def get_boundaries(rect, tiles):
    deltas = {D.n: P(0, -1), D.e: P(1, 0), D.s: P(0, 1), D.w: P(-1, 0)}
    return {d for d, delta in deltas.items() if rect.move(delta).collidelist(tiles) != -1}

def stop_on_collision(spd, bounds):
    return P(x=0 if (D.w in bounds and spd.x < 0) or (D.e in bounds and spd.x > 0) else spd.x,
             y=0 if (D.n in bounds and spd.y < 0) or (D.s in bounds and spd.y > 0) else spd.y)

def draw(screen, images, mario, tiles, pressed):
    def get_marios_image_index():
        if D.s not in get_boundaries(mario.rect, tiles):
            return 4
        return next(mario.frame_cycle) if {D.w, D.e} & pressed else 6
    screen.fill((85, 168, 255))
    mario.facing_left = (D.w in pressed) if {D.w, D.e} & pressed else mario.facing_left
    screen.blit(images[get_marios_image_index() + mario.facing_left * 9], mario.rect)
    for t in tiles:
        screen.blit(images[18 if t.x in [0, (W-1)*16] or t.y in [0, (H-1)*16] else 19], t)
    pg.display.flip()

if __name__ == '__main__':
    main()
```

**[🔼Back to Top](#table-of-contents)**

## Pandas

```python
# $ pip3 install pandas matplotlib
import pandas as pd
from pandas import Series, DataFrame
import matplotlib.pyplot as plt
```

### Series

**Ordered dictionary with a name.**

```python
>>> Series([1, 2], index=['x', 'y'], name='a')
x    1
y    2
Name: a, dtype: int64
```

```python
<Sr> = Series(<list>)                          # Assigns RangeIndex starting at 0.
<Sr> = Series(<dict>)                          # Takes dictionary's keys for index.
<Sr> = Series(<dict/Series>, index=<list>)     # Only keeps items with keys specified in index.
```

```python
<el> = <Sr>.loc[key]                           # Or: <Sr>.iloc[index]
<Sr> = <Sr>.loc[keys]                          # Or: <Sr>.iloc[indexes]
<Sr> = <Sr>.loc[from_key : to_key_inclusive]   # Or: <Sr>.iloc[from_i : to_i_exclusive]
```

```python
<el> = <Sr>[key/index]                         # Or: <Sr>.key
<Sr> = <Sr>[keys/indexes]                      # Or: <Sr>[<key_range/range>]
<Sr> = <Sr>[bools]                             # Or: <Sr>.i/loc[bools]
```

```python
<Sr> = <Sr> ><== <el/Sr>                       # Returns a Series of bools.
<Sr> = <Sr> +-*/ <el/Sr>                       # Items with non-matching keys get value NaN.
```

```python
<Sr> = <Sr>.append(<Sr>)                       # Or: pd.concat(<coll_of_Sr>)
<Sr> = <Sr>.combine_first(<Sr>)                # Adds items that are not yet present.
<Sr>.update(<Sr>)                              # Updates items that are already present.
```

```python
<Sr>.plot.line/area/bar/pie/hist()             # Generates a Matplotlib plot.
plt.show()                                     # Displays the plot. Also plt.savefig(<path>).
```

#### Series — Aggregate, Transform, Map:

```python
<el> = <Sr>.sum/max/mean/idxmax/all()          # Or: <Sr>.agg(lambda <Sr>: <el>)
<Sr> = <Sr>.rank/diff/cumsum/ffill/interpl()   # Or: <Sr>.agg/transform(lambda <Sr>: <Sr>)
<Sr> = <Sr>.fillna(<el>)                       # Or: <Sr>.agg/transform/map(lambda <el>: <el>)
```

```python
>>> sr = Series([1, 2], index=['x', 'y'])
x    1
y    2
```

```text
+-----------------+-------------+-------------+---------------+
|                 |    'sum'    |   ['sum']   | {'s': 'sum'}  |
+-----------------+-------------+-------------+---------------+
| sr.apply(…)     |      3      |    sum  3   |     s  3      |
| sr.agg(…)       |             |             |               |
+-----------------+-------------+-------------+---------------+
```

```text
+-----------------+-------------+-------------+---------------+
|                 |    'rank'   |   ['rank']  | {'r': 'rank'} |
+-----------------+-------------+-------------+---------------+
| sr.apply(…)     |             |      rank   |               |
| sr.agg(…)       |     x  1    |   x     1   |    r  x  1    |
| sr.transform(…) |     y  2    |   y     2   |       y  2    |
+-----------------+-------------+-------------+---------------+
```

- **Last result has a hierarchical index. Use `'<Sr>[key_1, key_2]'` to get its values.**

**[🔼Back to Top](#table-of-contents)**

### DataFrame

**Table with labeled rows and columns.**

```python
>>> DataFrame([[1, 2], [3, 4]], index=['a', 'b'], columns=['x', 'y'])
   x  y
a  1  2
b  3  4
```

```python
<DF>    = DataFrame(<list_of_rows>)            # Rows can be either lists, dicts or series.
<DF>    = DataFrame(<dict_of_columns>)         # Columns can be either lists, dicts or series.
```

```python
<el>    = <DF>.loc[row_key, column_key]        # Or: <DF>.iloc[row_index, column_index]
<Sr/DF> = <DF>.loc[row_key/s]                  # Or: <DF>.iloc[row_index/es]
<Sr/DF> = <DF>.loc[:, column_key/s]            # Or: <DF>.iloc[:, column_index/es]
<DF>    = <DF>.loc[row_bools, column_bools]    # Or: <DF>.iloc[row_bools, column_bools]
```

```python
<Sr/DF> = <DF>[column_key/s]                   # Or: <DF>.column_key
<DF>    = <DF>[row_bools]                      # Keeps rows as specified by bools.
<DF>    = <DF>[<DF_of_bools>]                  # Assigns NaN to False values.
```

```python
<DF>    = <DF> ><== <el/Sr/DF>                 # Returns DF of bools. Sr is treated as a row.
<DF>    = <DF> +-*/ <el/Sr/DF>                 # Items with non-matching keys get value NaN.
```

```python
<DF>    = <DF>.set_index(column_key)           # Replaces row keys with values from a column.
<DF>    = <DF>.reset_index()                   # Moves row keys to a column named index.
<DF>    = <DF>.sort_index(ascending=True)      # Sorts rows by row keys.
<DF>    = <DF>.sort_values(column_key/s)       # Sorts rows by the passed column/s.
```

#### DataFrame — Merge, Join, Concat:

```python
>>> l = DataFrame([[1, 2], [3, 4]], index=['a', 'b'], columns=['x', 'y'])
   x  y
a  1  2
b  3  4
>>> r = DataFrame([[4, 5], [6, 7]], index=['b', 'c'], columns=['y', 'z'])
   y  z
b  4  5
c  6  7
```

```text
+------------------------+---------------+------------+------------+--------------------------+
|                        |    'outer'    |   'inner'  |   'left'   |       Description        |
+------------------------+---------------+------------+------------+--------------------------+
| l.merge(r, on='y',     |    x   y   z  | x   y   z  | x   y   z  | Joins/merges on column.  |
|            how=…)      | 0  1   2   .  | 3   4   5  | 1   2   .  | Also accepts left_on and |
|                        | 1  3   4   5  |            | 3   4   5  | right_on parameters.     |
|                        | 2  .   6   7  |            |            | Uses 'inner' by default. |
+------------------------+---------------+------------+------------+--------------------------+
| l.join(r, lsuffix='l', |    x yl yr  z |            | x yl yr  z | Joins/merges on row keys.|
|           rsuffix='r', | a  1  2  .  . | x yl yr  z | 1  2  .  . | Uses 'left' by default.  |
|           how=…)       | b  3  4  4  5 | 3  4  4  5 | 3  4  4  5 | If r is a Series, it is  |
|                        | c  .  .  6  7 |            |            | treated as a column.     |
+------------------------+---------------+------------+------------+--------------------------+
| pd.concat([l, r],      |    x   y   z  |     y      |            | Adds rows at the bottom. |
|           axis=0,      | a  1   2   .  |     2      |            | Uses 'outer' by default. |
|           join=…)      | b  3   4   .  |     4      |            | A Series is treated as a |
|                        | b  .   4   5  |     4      |            | column. Use l.append(sr) |
|                        | c  .   6   7  |     6      |            | to add a row instead.    |
+------------------------+---------------+------------+------------+--------------------------+
| pd.concat([l, r],      |    x  y  y  z |            |            | Adds columns at the      |
|           axis=1,      | a  1  2  .  . | x  y  y  z |            | right end. Uses 'outer'  |
|           join=…)      | b  3  4  4  5 | 3  4  4  5 |            | by default. A Series is  |
|                        | c  .  .  6  7 |            |            | treated as a column.     |
+------------------------+---------------+------------+------------+--------------------------+
| l.combine_first(r)     |    x   y   z  |            |            | Adds missing rows and    |
|                        | a  1   2   .  |            |            | columns. Also updates    |
|                        | b  3   4   5  |            |            | items that contain NaN.  |
|                        | c  .   6   7  |            |            | R must be a DataFrame.   |
+------------------------+---------------+------------+------------+--------------------------+
```

#### DataFrame — Aggregate, Transform, Map:

```python
<Sr> = <DF>.sum/max/mean/idxmax/all()          # Or: <DF>.apply/agg(lambda <Sr>: <el>)
<DF> = <DF>.rank/diff/cumsum/ffill/interpl()   # Or: <DF>.apply/agg/transfrm(lambda <Sr>: <Sr>)
<DF> = <DF>.fillna(<el>)                       # Or: <DF>.applymap(lambda <el>: <el>)
```

- **All operations operate on columns by default. Pass `'axis=1'` to process the rows instead.**

```python
>>> df = DataFrame([[1, 2], [3, 4]], index=['a', 'b'], columns=['x', 'y'])
   x  y
a  1  2
b  3  4
```

```text
+-----------------+-------------+-------------+---------------+
|                 |    'sum'    |   ['sum']   | {'x': 'sum'}  |
+-----------------+-------------+-------------+---------------+
| df.apply(…)     |             |       x  y  |               |
| df.agg(…)       |     x  4    |  sum  4  6  |     x  4      |
|                 |     y  6    |             |               |
+-----------------+-------------+-------------+---------------+
```

```text
+-----------------+-------------+-------------+---------------+
|                 |    'rank'   |   ['rank']  | {'x': 'rank'} |
+-----------------+-------------+-------------+---------------+
| df.apply(…)     |      x  y   |      x    y |        x      |
| df.agg(…)       |   a  1  1   |   rank rank |     a  1      |
| df.transform(…) |   b  2  2   | a    1    1 |     b  2      |
|                 |             | b    2    2 |               |
+-----------------+-------------+-------------+---------------+
```

- **Use `'<DF>[col_key_1, col_key_2][row_key]'` to get the fifth result's values.**

#### DataFrame — Plot, Encode, Decode:

```python
<DF>.plot.line/bar/hist/scatter/box()          # Also: `x=column_key, y=column_key/s`.
plt.show()                                     # Displays the plot. Also plt.savefig(<path>).
```

```python
<DF> = pd.read_json/html('<str/path/url>')     # Run `$ pip3 install beautifulsoup4 lxml`.
<DF> = pd.read_csv/pickle/excel('<path/url>')  # Use `sheet_name=None` to get all Excel sheets.
<DF> = pd.read_sql('<table/query>', <conn.>)   # Accepts SQLite3 or SQLAlchemy connection.
<DF> = pd.read_clipboard()                     # Reads a copied table from the clipboard.
```

```python
<dict> = <DF>.to_dict(['d/l/s/…'])             # Returns columns as dicts, lists or series.
<str>  = <DF>.to_json/html/csv([<path>])       # Also to_markdown/latex([<path>]).
<DF>.to_pickle/excel(<path>)                   # Run `$ pip3 install openpyxl` for xlsx files.
<DF>.to_sql('<table_name>', <connection>)      # Accepts SQLite3 or SQLAlchemy connection.
```

### GroupBy

**Object that groups together rows of a dataframe based on the value of the passed column.**

```python
>>> df = DataFrame([[1, 2, 3], [4, 5, 6], [7, 8, 6]], index=list('abc'), columns=list('xyz'))
>>> df.groupby('z').get_group(6)
   x  y
b  4  5
c  7  8
```

```python
<GB> = <DF>.groupby(column_key/s)              # Splits DF into groups based on passed column.
<DF> = <GB>.apply(<func>)                      # Maps each group. Func can return DF, Sr or el.
<GB> = <GB>[column_key]                        # Single column GB. All operations return a Sr.
```

#### GroupBy — Aggregate, Transform, Map:

```python
<DF> = <GB>.sum/max/mean/idxmax/all()          # Or: <GB>.agg(lambda <Sr>: <el>)
<DF> = <GB>.rank/diff/cumsum/ffill()           # Or: <GB>.transform(lambda <Sr>: <Sr>)
<DF> = <GB>.fillna(<el>)                       # Or: <GB>.transform(lambda <Sr>: <Sr>)
```

```python
>>> gb = df.groupby('z')
      x  y  z
3: a  1  2  3
6: b  4  5  6
   c  7  8  6
```

```text
+-----------------+-------------+-------------+-------------+---------------+
|                 |    'sum'    |    'rank'   |   ['rank']  | {'x': 'rank'} |
+-----------------+-------------+-------------+-------------+---------------+
| gb.agg(…)       |      x   y  |      x  y   |      x    y |        x      |
|                 |  z          |   a  1  1   |   rank rank |     a  1      |
|                 |  3   1   2  |   b  1  1   | a    1    1 |     b  1      |
|                 |  6  11  13  |   c  2  2   | b    1    1 |     c  2      |
|                 |             |             | c    2    2 |               |
+-----------------+-------------+-------------+-------------+---------------+
| gb.transform(…) |      x   y  |      x  y   |             |               |
|                 |  a   1   2  |   a  1  1   |             |               |
|                 |  b  11  13  |   b  1  1   |             |               |
|                 |  c  11  13  |   c  2  2   |             |               |
+-----------------+-------------+-------------+-------------+---------------+
```

### Rolling

**Object for rolling window calculations.**

```python
<RSr/RDF/RGB> = <Sr/DF/GB>.rolling(win_size)   # Also: `min_periods=None, center=False`.
<RSr/RDF/RGB> = <RDF/RGB>[column_key/s]        # Or: <RDF/RGB>.column_key
<Sr/DF>       = <R>.mean/sum/max()             # Or: <R>.apply/agg(<agg_func/str>)
```

## Plotly

```python
# $ pip3 install plotly kaleido
from plotly.express import line
<Figure> = line(<DF>, x=<col_name>, y=<col_name>)        # Or: line(x=<list>, y=<list>)
<Figure>.update_layout(margin=dict(t=0, r=0, b=0, l=0))  # Or: paper_bgcolor='rgba(0, 0, 0, 0)'
<Figure>.write_html/json/image('<path>')                 # Also: <Figure>.show()
```

#### Covid deaths by continent:

![Covid Deaths](web/covid_deaths.png)

<div id="2a950764-39fc-416d-97fe-0a6226a3095f" class="plotly-graph-div" style="height:340px; width:100%;"></div>

```python
covid = pd.read_csv('https://covid.ourworldindata.org/data/owid-covid-data.csv',
                    usecols=['iso_code', 'date', 'total_deaths', 'population'])
continents = pd.read_csv('https://gist.githubusercontent.com/stevewithington/20a69c0b6d2ff'
                         '846ea5d35e5fc47f26c/raw/country-and-continent-codes-list-csv.csv',
                         usecols=['Three_Letter_Country_Code', 'Continent_Name'])
df = pd.merge(covid, continents, left_on='iso_code', right_on='Three_Letter_Country_Code')
df = df.groupby(['Continent_Name', 'date']).sum().reset_index()
df['Total Deaths per Million'] = df.total_deaths * 1e6 / df.population
df = df[df.date > '2020-03-14']
df = df.rename({'date': 'Date', 'Continent_Name': 'Continent'}, axis='columns')
line(df, x='Date', y='Total Deaths per Million', color='Continent').show()
```

#### Confirmed covid cases, Dow Jones, Gold, and Bitcoin price:

![Covid Cases](web/covid_cases.png)

<div id="e23ccacc-a456-478b-b467-7282a2165921" class="plotly-graph-div" style="height:315px; width:100%;"></div>

```python
import pandas as pd
import plotly.graph_objects as go

def main():
    display_data(wrangle_data(*scrape_data()))

def scrape_data():
    def scrape_covid():
        url = 'https://covid.ourworldindata.org/data/owid-covid-data.csv'
        df = pd.read_csv(url, usecols=['location', 'date', 'total_cases'])
        return df[df.location == 'World'].set_index('date').total_cases
    def scrape_yahoo(slug):
        url = f'https://query1.finance.yahoo.com/v7/finance/download/{slug}' + \
              '?period1=1579651200&period2=9999999999&interval=1d&events=history'
        df = pd.read_csv(url, usecols=['Date', 'Close'])
        return df.set_index('Date').Close
    out = scrape_covid(), scrape_yahoo('BTC-USD'), scrape_yahoo('GC=F'), scrape_yahoo('^DJI')
    return map(pd.Series.rename, out, ['Total Cases', 'Bitcoin', 'Gold', 'Dow Jones'])

def wrangle_data(covid, bitcoin, gold, dow):
    df = pd.concat([bitcoin, gold, dow], axis=1)  # Joins columns on dates.
    df = df.sort_index().interpolate()            # Sorts by date and interpolates NaN-s.
    df = df.loc['2020-02-23':]                    # Discards rows before '2020-02-23'.
    df = (df / df.iloc[0]) * 100                  # Calculates percentages relative to day 1.
    df = df.join(covid)                           # Adds column with covid cases.
    return df.sort_values(df.index[-1], axis=1)   # Sorts columns by last day's value.

def display_data(df):
    figure = go.Figure()
    for col_name in reversed(df.columns):
        yaxis = 'y1' if col_name == 'Total Cases' else 'y2'
        trace = go.Scatter(x=df.index, y=df[col_name], name=col_name, yaxis=yaxis)
        figure.add_trace(trace)
    figure.update_layout(
        yaxis1=dict(title='Total Cases', rangemode='tozero'),
        yaxis2=dict(title='%', rangemode='tozero', overlaying='y', side='right'),
        legend=dict(x=1.1),
        height=450
    ).show()

if __name__ == '__main__':
    main()
```

## PySimpleGUI

```python
# $ pip3 install PySimpleGUI
import PySimpleGUI as sg
layout = [[sg.Text("What's your name?")], [sg.Input()], [sg.Button('Ok')]]
window = sg.Window('Window Title', layout)
event, values = window.read()
print(f'Hello {values[0]}!' if event == 'Ok' else '')
```

## Matplotlib

**Header:**
```python
import numpy as np
import random
import matplotlib.pyplot as plt
```

**Plotting an equation:**
```python
fig, ax = plt.subplots()
x = np.random.randint(1,10, size=10)
y = x 
plt.plot(x,y)
plt.show()
```
The above code would plot the line x = y.

**Plotting multiple equations:**
```python
fig, ax = plt.subplots()
x = np.random.randint(1,10, size=10)
y = x 
plt.plot(x,y)
plt.plot(x,x+3)
plt.show()
```

**Changing color or style of lines:**
```python
plt.plot(x, y, color='ENTER COLOR NAME HERE', linestyle='DRAW LINESTYLE HERE')
```
Available linestyles:
1) --
2) :
3) -.
   
**Setting graph limits:**
```python
plt.xlim(x1,y1)
plt.ylim(x2, y2)
```

**Labelling the axis:**
```python
plt.xlabel("TITLE GOES HERE")
plt.ylabel("TITLE GOES HERE")
```

**Title of the graph:**
```python
plt.title("TITLE GOES HERE")
```

**Make a scatter graph:**
```python
plt.scatter(x,y)
```

**Make a area chart:**
```python
plt.fill_between( x, y, color="ENTER COLOR HERE", alpha=ENTER ALPHA HERE)
```

**Make a bar graph**
```python
plt.bar(y, data, align='ENTER ALIGNMENT HERE', alpha=ENTER ALPHA HERE)
```

**Make a pie chart:**
```python
plt.pie(data, labels=labels, explode=(x, x, ... x))
```

**[🔼Back to Top](#table-of-contents)**


## Appendix

### Cython

**Library that compiles Python code into C.**

```python
# $ pip3 install cython
import pyximport; pyximport.install()
import <cython_script>
<cython_script>.main()
```

#### Definitions:

- **All `'cdef'` definitions are optional, but they contribute to the speed-up.**
- **Script needs to be saved with a `'pyx'` extension.**

```python
cdef <ctype> <var_name> = <el>
cdef <ctype>[n_elements] <var_name> = [<el_1>, <el_2>, ...]
cdef <ctype/void> <func_name>(<ctype> <arg_name>): ...
```

```python
cdef class <class_name>:
    cdef public <ctype> <attr_name>
    def __init__(self, <ctype> <arg_name>):
        self.<attr_name> = <arg_name>
```

```python
cdef enum <enum_name>: <member_name_1>, <member_name_2>, ...
```

### PyInstaller

```bash
$ pip3 install pyinstaller
$ pyinstaller script.py                        # Compiles into './dist/script' directory.
$ pyinstaller script.py --onefile              # Compiles into './dist/script' console app.
$ pyinstaller script.py --windowed             # Compiles into './dist/script' windowed app.
$ pyinstaller script.py --add-data '<path>:.'  # Adds file to the root of the executable.
```

- **File paths need to be updated to `'os.path.join(sys._MEIPASS, <path>)'`.**

### Basic Script Template

```python
#!/usr/bin/env python3
#
# Usage: .py
#

from sys import argv, exit
from collections import defaultdict, namedtuple
from dataclasses import make_dataclass
from enum import Enum
import functools as ft, itertools as it, operator as op, re


def main():
    pass


###
##  UTIL
#

def read_file(filename):
    with open(filename, encoding='utf-8') as file:
        return file.readlines()


if __name__ == '__main__':
    main()
```

## Index

- **Only available in the [PDF](https://transactions.sendowl.com/products/78175486/4422834F/view).**
- **Ctrl+F / ⌘F is usually sufficient.**
- **Searching `'#<title>'` on the [webpage](https://gto76.github.io/python-cheatsheet/) will limit the search to the titles.**

**[🔼Back to Top](#table-of-contents)**
