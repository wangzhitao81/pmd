---
title: Braces
summary: The Braces Ruleset contains a collection of braces rules.
permalink: pmd_rules_ecmascript_braces.html
folder: pmd/rules/ecmascript
sidebaractiveurl: /pmd_rules_ecmascript.html
editmepath: ../pmd-javascript/src/main/resources/rulesets/ecmascript/braces.xml
keywords: Braces, IfStmtsMustUseBraces, IfElseStmtsMustUseBraces, WhileLoopsMustUseBraces, ForLoopsMustUseBraces
---
## ForLoopsMustUseBraces

**Since:** PMD 5.0

**Priority:** Medium (3)

Avoid using 'for' statements without using curly braces.

```
//ForLoop[not(child::Scope)]
|
//ForInLoop[not(child::Scope)]
```

**Example(s):**

``` javascript
// Ok
for (var i = 0; i < 42; i++) {
    foo();
}

// Bad
for (var i = 0; i < 42; i++)
    foo();
```

**Use this rule by referencing it:**
``` xml
<rule ref="rulesets/ecmascript/braces.xml/ForLoopsMustUseBraces" />
```

## IfElseStmtsMustUseBraces

**Since:** PMD 5.0

**Priority:** Medium (3)

Avoid using if..else statements without using curly braces.

```
//ExpressionStatement[parent::IfStatement[@Else = "true"]]
   [not(child::Scope)]
   [not(child::IfStatement)]
```

**Example(s):**

``` javascript
// Ok
if (foo) {
    x++;
} else {
    y++;
}

// Bad
if (foo)
    x++;
else
    y++;
```

**Use this rule by referencing it:**
``` xml
<rule ref="rulesets/ecmascript/braces.xml/IfElseStmtsMustUseBraces" />
```

## IfStmtsMustUseBraces

**Since:** PMD 5.0

**Priority:** Medium (3)

Avoid using if statements without using curly braces.

```
//IfStatement[@Else = "false" and not(child::Scope)]
```

**Example(s):**

``` javascript
// Ok
if (foo) {
    x++;
}

// Bad
if (foo)
    x++;
```

**Use this rule by referencing it:**
``` xml
<rule ref="rulesets/ecmascript/braces.xml/IfStmtsMustUseBraces" />
```

## WhileLoopsMustUseBraces

**Since:** PMD 5.0

**Priority:** Medium (3)

Avoid using 'while' statements without using curly braces.

```
//WhileLoop[not(child::Scope)]
```

**Example(s):**

``` javascript
// Ok
while (true) {
    x++;
}

// Bad
while (true)
    x++;
```

**Use this rule by referencing it:**
``` xml
<rule ref="rulesets/ecmascript/braces.xml/WhileLoopsMustUseBraces" />
```

