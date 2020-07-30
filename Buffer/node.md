# 常用的进制
- 10进制 2进制 0b 8进制 0o(可省略成0) 16进制 0x 【不同的进制可以表示一个值】
- 进制转化的方法
    - 编码过程中都是以字节为单位
    - 一个字节是有8个bit位组成。编码都是以字节为单位。 一个字节为一个字符，双字节组成汉字，UTF-8中三个字节为一个汉字。
    - 把任意进制转换成十进制，需要用当前位所在的值*进制第几位
    - 把10进制转换成任意进制，除取余。

    ```js
        console.log(parseInt(22,'8')); // 将任意进制转换成十进制
        console.log(2..toString('8')); // 将十进制转换成任意进制
    ```

- Node中需要文件读取，node中操作的内容默认会存在内存中，内存中的表现是二进制，用16进制展现。

```js
const fs = require('fs');
let r = fs.readFileSync('./node.md');
console.log(r.toString());
```

# 编码的发展史
- ASCII 编码一些常用的符号和字母 进行了一些排号 127 只会占用一个字节大小
- GB2312 用两个字节 27000
- GBK 国标扩展 40000
- GB18030 少数民族汉字
- Unicode 组织 发表了编码
- UTF-8 (在UTF-8一个字符一个字节，一个汉字三个字节)。开发过程中一般使用UTF-8。

# base64 没有加密功能，只是编码
- 减少http请求。【比如图片】
- 3*8的规则改成了4*6的方式
- 小图标适合 base 64 转码。base64 会使文件加大。
- gzip 重复性高的可以压缩，

# 前端的二进制
- 文件类型Blob 
- 