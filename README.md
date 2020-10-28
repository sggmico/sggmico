<!--
**szjxxy/szjxxy** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

### hi，请听题！ - 2020.10.26 -  👇

**标签**：`编程题`

1、`2 ** 53 + 1` 结果是？为什么？正解如何计算?

```html
考察点：
    1. js大数计算精度问题
    2. 字符串操作
    3. 解法的多样性
    4. ES10的更新
    5. code style
```
题解
```js
// 解法一：使用字符串，控制进位
function bigNumberSum(x, y) {
    x = +x
    y = +y 
    if([x, y].filter(num => Number.isSafeInteger(num)).length === 2) {
        return x + y 
    }

    x = '' + x 
    y = '' + y 
    var xLen = x.length,
        yLen = y.length,
        carried = 0,
        res = []

    if(xLen - yLen > 0) {
        y = y.padStart(xLen, '0')
    } else {
        x = x.padStart(yLen, '0')        
    }

    for(var i = x.length - 1; i > -1; i--) {
       var sum = +x[i] + +y[i] + carried
        if(sum > 9) {
            carried = 1
        } else {
            carried = 0
        }
        res.unshift( sum % 10 )
    }
    if(carried === 1) res.unshift(1)
    return res.join('')
}

// 解法二：使用 ES10新增 BigInt 数据类型。 缺点：兼容性不足
function bigNumberSum(x, y) {
    let sum = BigInt(x) + BigInt(y)
    return sum.toString()
}

// 解法三：使用第三方库。
    bignumber.js : https://github.com/MikeMcl/bignumber.js/
```

 👉   **[题板](https://github.com/szjxxy/fe-happy-interview/issues/2)**

🚀    **[更多](https://github.com/szjxxy/fe-happy-interview/issues)**
### Follow Me 🕸

- [个人网站](http://fe.teachclass.cn/)
- [知乎](http://fe.teachclass.cn/)
- [掘金](http://fe.teachclass.cn/)
- [微信公众号 -【乘风破浪大前端】](http://fe.teachclass.cn/)
