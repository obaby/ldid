# ldid
ldid's mirror.
3. 编译

$ cd ldid-1.0.610
$ g++ -I . -o util/ldid{,.cpp} -x c util/{lookup2,sha1}.c
4. 放到系统bin目录

$ sudo cp -a util/ldid /usr/bin
5. 执行

$ ldid -S FILE

 

6. 错误处理
直接执行ldid -S  yourlib可能会出现如下错误：

util/ldid.cpp(576): _assert(2:false)
util/ldid.cpp(581): _assert(0:WIFEXITED(status))
Trace/breakpoint trap


需要设定CODESIGN_ALLOCATE环境变量：
export CODESIGN_ALLOCATE= $(your_toolchain)/toolchain/pre/bin/arm-apple-darwin9-codesign_allocate
ldid -S  your.dylib
