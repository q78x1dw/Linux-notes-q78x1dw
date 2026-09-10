# Data Types

|data type  |descriptions|
|---------  |------------|
|nil        |only `nil` belongs to this. ineffective value|
|boolean    |`false` `true`|
|number     |==`double` in C|
|string     |use `""` `''`|
|function   |written in C or lua|
|userdata   |any C datastructures stored in a var|
|thread     | ....... |
|*table*    | associative arrays, can be indexed by nums strs or other tables|

## nil
assign nil == delete

**reminder** `type()` returns a STRING

## boolean

`false` and `nil` considered false, others **(including 0)** true

## string

`
text = [[
    this is a block of string.
]]
`
string concatenate: `"a" .. "b"` (with spaces inside)
strlen: `#"string"` `#string_var` (without \0 ends blabla)

## table

create table :**construction expression**

assocative array: default index grows from **1**

## function
functions are 1st-class values ; store in variables -> ok!

### anonymous
` func = function(arg1,arg2,...)stat1;stat2;return stat3; end

## thread

coroutine

## userdata 
customized by app or C/C++

