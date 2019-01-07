# router

For exp3, use the following command to generate rip executable file:

```bash
g++ rip.cpp -orip -O2 -lpthread -DRIP_MAIN

# RUN:
./rip
```

For exp4, just type `mv lookuproute_simple.cpp.bak lookuproute.cpp; make -j` and run `sudo ./main`.

由于为了后续性能，把输出的部分给注释掉了。

## Additional exp

编译：直接 `make -j`

就写了个哈希边表，每次从/32查到/1，看看有没有对应的路由表项

可以理解为我开了32个数组，但是存的时候存得紧凑了点

该算法代码位于 `lookuproute.cpp` 中，不到30行（后面常数优化了一波，循环展开，做到差不多和4位trie一样快了，代码翻了一倍）

事实上是/32到/13存hash，/12到/1直接数组存下来
