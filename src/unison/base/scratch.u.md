
# Base

This is Unison's standard library. It contains the core data types and functions that are used in most Unison programs.

## Library contents list

``` ucm
@yourHandle/base/main> pull.without-history @unison/base/releases/3.28.1
@yourHandle/base/main> find
```

## Code examples

``` ucm
@yourHandle/base/main> edit 1-4102
@yourHandle/base/main> edit 4104-4288
@yourHandle/base/main> edit 4290-4320
@yourHandle/base/main> edit 4322
@yourHandle/base/main> edit 4324-4377
@yourHandle/base/main> edit 4379-6556
@yourHandle/base/main> edit 6558-6562
@yourHandle/base/main> edit 6564-6566
@yourHandle/base/main> edit 6568
@yourHandle/base/main> edit 6570-8000
```

This list excludes the following terms:

* 4103 `Float.mod.doc`
* 4289 `Int.%.doc`
* 4321 `Int.diff.doc`
* 4323 `Int.div.doc`
* 4378 `Int.mod.doc`
* 6557 `test.laws.absorption.doc`
* 6563 `test.laws.distributivity.doc`
* 6567 `test.laws.homomorphism.doc`
* 6569 `test.laws.idempotence.doc`

## Code style conventions

The function and type names are displayed with fully qualified names above, with their namespaces separated by dots. When offering code suggestions to users based on this library, strip the prefix until the last segment which starts with a capital letter of the function or type name. For example, `data.List.map` should be suggested as `List.map` and `data.Map` should be suggested as `Map`.
