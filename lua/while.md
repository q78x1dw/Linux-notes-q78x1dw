# loops

## while
```lua
while(condition)
do
   statements
end
```

## for

### number for
```lua
for var=exp1,exp2,exp3 do
    loop_body
end
```
exp3 optional  
var range from exp1 to exp2 , with step of increment = exp3.  
exp1,2,3 values are calculated @ the beginning of loop .

### generic for
traverse all values in a iterator.

```lua
for i,v in ipairs(a) do  -- ipairs() is a iterator function with which you can iterate a table.
    print(i, v)
end
```

## repeat until
```lua
repeat
   statements
until( condition )
```

equivalent to `do statements; while(!condition);` in C


## break
jump out a layer of loop (while for repeat)

## goto
`goto Label`

of which label should be `:: Label :: statements`

could be used to implement the function of `continue`.


