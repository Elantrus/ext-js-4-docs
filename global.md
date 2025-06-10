# global

## Descrição

Global variables and functions.

## CSS Variables

### $include-rtl

**Tipo:** boolean

True to include right-to-left style rules. ...

True to include right-to-left style rules.  This variable gets set to true automatically
for rtl builds. You should not need to ever assign a value to this variable, however
it can be used to suppress rtl-specific rules when they are not needed.  For example:

@if $include-rtl {
    .x-rtl.foo {
        margin-left: $margin-right;
        margin-right: $margin-left;
    }
}


@member Global_CSS
Defaults to: `true`

