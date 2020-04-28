```javascript
let params = {
    data1: 1,
    data2: 2,
    data3: 3
}

// this.$axios.get(url, params) 这个params必须要加上{}才能传输出去
// this.$axios.get(url,{ params }) 这样子就可以带参传输了
// get方法需要在params对象外面再套一层对象； post方法就不需要
// this.$axios.post(url, params) 这个就可以直接带上params传输出去
```

