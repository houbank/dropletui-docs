# search

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| v-model |  | string |  |  |
| autofocus |  | boolean |  | false |
| bgColor |  | string |  | \#d9d9d9 |
| placeholder |  | string |  | 搜索 |
| cancelColor |  | string |  | \#4d4d4d |
| innerBgColor |  | string |  | \#fff |

## slot

| name | 说明 |
| :--- | :--- |


## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |


## Usage

```
<template>
    <div>
        <wx-search
            v-model="searchContent1">
        </wx-search>
        <div class="result m-b-20">
            <text class="f32">{{searchContent1}}</text>
        </div>

        <wx-search
            v-model="searchContent2"
            placeholder="请输入"
            :autofocus="true"
            bgColor="#4676FF"
            innerBgColor="#fff"
            cancelColor="#fff">
        </wx-search>
        <div class="result m-b-20">
            <text class="f32">{{searchContent2}}</text>
        </div>
    </div>
</template>

<script>
    import WxSearch from 'weex-droplet-ui'

    export default {
        data () {
            return {
                searchContent1: '',
                searchContent2: ''
            }
        },

        methods: {

        },

        components: {WxSearch}
    }
</script>
<style scoped>
    .result {
        width: 750px;
        height: 40px;
    }
    .m-b-20 {
        margin-bottom: 20px;
    }
    .f32 {
        font-size: 32px;
    }
</style>

```



