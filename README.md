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
| **"_string_"**        | punctuation.definition.string.begin.rpl<br> _string.rpl_<br> punctuation.definition.string.end.rpl<br> Escaped characters: constant.character.escape.rpl |
| pat**\***     | keyword.operator.repetition.star.rpl |
| pat**+**      | keyword.operator.repetition.plus.rpl |
| pat**?**      | keyword.operator.repetition.optional.rpl |
| pat**{_n_,_m_}**  | keyword.operator.repetition.range.rpl<br> _keyword.operator.repetition.range.from.rpl_<br> _keyword.operator.repetition.range.to.rpl_ |
| **!**pat      | keyword.operator.negation.rpl |
| **@**pat      | keyword.operator.peek.rpl |
| p **/** q       | keyword.operator.choice.rpl |
| **(**...**)**   | keyword.operator.group.cooked.rpl |
| **{**...**}**   | keyword.operator.group.raw.rpl |
| **[:name:]**    | constant.class.named.rpl |
| **[x-y]**       | constant.class.range.rpl |
| **[...]**       | constant.class.list.rpl |
| **[^:name:]**    | constant.class.named.negated.rpl |
| **[^x-y]**       | constant.class.range.negated.rpl |
| **[^...]**       | constant.class.list.negated.rpl |
| **[** cs1 cs2 **]** | constant.class.union.rpl |
| **[^** cs1 cs2 **]** | constant.class.union.negated.rpl |
| **-- test** id **command** ... | keyword.test.rpl<br> keyword.test.command.rpl |
| **-- comment...** | comment.rpl |
| **namespace.pattern** | entity.name.namespace.rpl<br> keyword.operator.rpl<br> entity.name.pattern.rpl |
| **grammar** ... **end** | storage.function.rpl |
| **local** | storage.modifier.rpl |
| **alias** | storage.type.rpl |
| **rpl _dd_.dd** | keyword.control.rpl<br> _constant.numeric.version.major.rpl_<br> constant.numeric.version.minor.rpl |
| pat **=** exp | keyword.operator.assignment.rpl |

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
