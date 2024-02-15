# 4280 Project 2 Parser

## How to run
1. run make clean command to clean any old builds
2. run make
3. start program by typing ./P2 [testFile]

## Known issues
For badFile7.f23 even though the parser knows there is an extra token after the EOF token it is still trying to print the tree

## Task

### BNF
```
<program> -> <vars> xopen <stats> xclose
<vars>    -> empty | xdata <varList>
<varList> -> identifier : integer <Y>
<Y>       -> ; | <varList>
<exp>     -> <M> <X>
<X>       -> / <exp> | * <exp> | empty
<M>       -> <N> <Z>
<Z>       -> + <M> | empty
<N>       -> <R> - <N> | ~<N> | <R>
<R>       -> ( <exp> ) | identifier | integer
<stats>   -> <stat> <mStat>
<mStat>   -> empty | <stat> <mStat>
<stat>    -> <in> | <out> | <block> | <if> | <loop> | <assign>
<block>   -> {<vars> <stats>}
<in>      -> xin >> identifier;
<out>     -> xout << <exp>;
<if>      -> xcond [<exp> <RO> <exp>] <stat>
<loop>    -> xloop [<exp> <RO> <exp>] <stat>
<assign>  -> xlet identifier <exp>;
<R0>      -> <<(onetoken) | >> (one token) | < | >| = | %
```
