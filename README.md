Rosie Pattern Language support in Atom
======

Add syntax highlighting and snippets to Rosie Pattern Language files in Atom.

Rosie Pattern Language:  
https://github.com/jamiejennings/rosie-pattern-language

Based on the in development v1.1 RPL spec:  
https://github.com/jamiejennings/rosie-pattern-language/blob/tranche-3/rpl/rpl-1.1.rpl.

Syntax CSS Class Scope
------

| RPL expression  | Scope      |
|-----------------|------------|
| "string"        | punctuation.definition.string.begin.rpl<br> _string.rpl_<br> punctuation.definition.string.end.rpl<br> Escaped characters: constant.character.escape.rpl |
| *, +, ?, {n,m}  | keyword.operator.quantifier.rpl |
| !, @            | keyword.operator.lookahead.[not,at].rpl |
| =               | keyword.operator.assignment.rpl |
| ( ... )         | keyword.operator.group.cooked.rpl<br> meta.group.cooked.rpl |
| { ... }         | keyword.operator.group.raw.rpl<br> meta.group.raw.rpl |
| /               | keyword.control.choice.rpl |
| [:name:]<br>[^:name:] | constant.other.class.named.rpl<br> constant.other.class.named.negated.rpl |
| [x-y]<br>[^x-y] | constant.other.class.range.rpl<br> constant.other.class.range.negated.rpl |
| [abc]<br>[^abc] | constant.other.class.list.rpl<br> constant.other.class.list.negated.rpl |
| [ cs1 cs2 ]<br>[^ cs1 cs2 ] | constant.other.class.union.rpl<br> constant.other.class.union.negated.rpl<br> meta.class.union.rpl |
| -- test id command ... | keyword.other.test.rpl<br>keyword.other.test.command.rpl<br> meta.test.rpl |
| -- comment | comment.rpl |
| namespace.pattern | support.class.rpl<br> variable.rpl |
| grammar<br>&nbsp;&nbsp;...<br>end<br><br>local | storage.type.rpl |
| alias | storage.modifier.rpl |
| rpl x.y | keyword.control.rpl<br> constant.numeric.version.major.rpl<br> constant.numeric.version.minor.rpl |
| import name as name | keyword.control.rpl<br> ident<br> keyword.operator.rpl<br> ident |
| package name | keyword.control.rpl<br> ident |

Snippets
-----

| Trigger | Name                | Body |
|---------|---------------------|------|
| lal     | local alias pattern | local alias name = expression |
| al      | alias pattern       | alias name = expression |
| lo      | local pattern       | local name = expression |
| gram    | grammar pattern     | grammar<br>&nbsp;&nbsp;grammar_name<br>end |
| testa   | accept test         | -- test name accepts "string" |
| testr   | reject test         | -- test name rejects "string" |

Author
------
__Kevin Zander__
* [https://github.com/Veratil](https://github.com/Veratil)


License
------
Atom language-rpl is released under the MIT license.
