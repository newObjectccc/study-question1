```javascript
<transition name="fade-transform" mode="out-in">
    <router-view :key="key"></router-view>
</transition>

// computed: {
//     key() {
//     return this.$route.path
//     }
// },

// 不生效是因为需要为 router-view 添加 :key="key"
// 这样 vue 才能正确解析每个 router-view ，因为 vue 是靠 key 来实现对router-view管理的

```

