# SCSS-lint Regex

I got tired of cleaning Sass codebases by hand to make them compliant with [SCSS-lint](https://github.com/brigade/scss-lint) so I wrote a set of regular expressions to do just that. 

The point is to be able to perform a quick search and replace to make the whole codebase compliant to a specific rule from SCSS-lint — when possible of course. Turned out to be extremely easy in Sublime Text for instance (see following screenshot).

![Search and replace in Sublime Text](http://i.imgur.com/hnWTib8.png)

If you suspect a regular expression to be incorrect, dangerous or improvable, please by all mean open a new issue so we can discuss it!

**[BangFormat](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#bangformat)**

* Search: `([^\s])!important`
* Replace: `\1 !important`

**[BorderZero](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#borderzero)**

* Search: `border:\s*none`
* Replace: `border: 0`

**[Comment](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#comment)**

A bit complex, but could probably be done.

**[DebugStatement](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#debugstatement)**

* Search: `^@debug.+$`
* Replace: nothing

**[DuplicateProperty](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#duplicateproperty)**

Hard, but could be done I suppose.

**[ElsePlacement](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#elseplacement)**

* Search: `}\s*@else`
* Replace: `} @else`

**[EmptyLineBetweenBlocks](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#emptylinebetweenblocks)**

Could be done.

**[EmptyRule](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#emptyrule)**

* Search: `^([^\n{]+){(?:|\s+)}\n`
* Replace: nothing 

**[FinalNewline](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#finalnewline)**

Could be done I suppose.

**[HexLength](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#hexlength)**

* Search: `#(?:([a-fA-F0-9])\1)(?:([a-fA-F0-9])\2)(?:([a-fA-F0-9])\3)`
* Replace: `#\1\2\3`

**[HexNotation](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#hexnotation)**

* Search: `(#[a-zA-Z0-9]{6}|[a-zA-Z0-9]{3})`
* Replace: `\L\1\E` (to lowercase) or `\U\1\E` (to uppercase)

**[ImportPath](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#importpath)**

* Search: `^@import\s+('|")_?(.*?)(?:.scss)?\1;`
* Replace: `@import \1\2\1;`

**[Indentation](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#indentation)**

Could theoretically be possible I guess.

**[LeadingZero](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#leadingzero)**

* Search: `\s+0\.(\d+)`
* Replace: `\ .\1`

**[NameFormat](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#nameformat)**

* Search: `([a-z])([A-Z])`
* Replace: `\1-\L\2\E`

*Note: remember to enable case sensitiveness.*

*Note: will also affect selectors. Could be optimised to only affect variables, placeholders, mixins and functions.*

**[PseudoElement](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#pseudoelement)**

* Search: `([^:]):(before|after|first-line|first-letter)`
* Replace: `\1::\2`

**[Shorthand](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#shorthand)**

Could be doable.

**[SingleLinePerProperty](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#singlelineperproperty)**

* Search: `;(?!\n)\s*`
* Replace: `;\n`

*Note: currently does not apply indentation.*

**[SingleLinePerSelector](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#singlelineperselector)**

Could be doable.

**[SpaceAfterComma](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#spaceaftercomma)**

* Search: `,([^\s])`
* Replace: `, \1`

**[SpaceAfterPropertyColon](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#spaceafterpropertycolon)**

* Search: `:(?:|\s{2,})([^\s])`
* Replace: `: \1`

**[SpaceAfterPropertyName](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#spaceafterpropertyname)**

Could be doable.

**[SpaceAfterVariableColon](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#spaceaftervariablecolon)**

Could be doable.

**[SpaceAfterVariableName](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#spaceaftervariablename)**

Could be doable.

**[SpaceAroundOperator](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#spacearoundoperator)**

Could be doable.

**[SpaceBeforeBrace](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#spacebeforebrace)**

* Search `([^\s]){`
* Replace: `\1 {`

**[SpaceBetweenParens](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#spacebetweenparens)**

* Search: `\(\s+([^()]+)\s+\)`
* Replace: `(\1)`

*Note: does not deal with nested parentheses.*

**[StringQuotes](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#stringquotes)**

* Search: `"`
* Replace: `'`

**[TrailingSemicolon](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#trailingsemicolon)**

Could be doable.

**[TrailingWhitespace](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#trailingwhitespace)**

* Search: `[ \t]+$`
* Replace: nothing

**[TrailingZero](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#trailingzero)**

Could be doable.

**[TransitionAll](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#transitionall)**

Could be doable.

**[UrlQuotes](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#urlquotes)**

* Search: `url\(([^\s'"]+)\)`
* Replace: `url('\1')` (or `url("\1")`)

**[VendorPrefix](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#vendorprefix)**

Could be doable.

**[ZeroUnit](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md#zerounit)**

* Search: `0(?!s|ms)(\w+)`
* Replace: `0`
