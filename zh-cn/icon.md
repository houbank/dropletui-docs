# icon

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| name | 箭头名称 | string |  | list中有什么值用什么值 |
| styles | 常规样式 | object |  |  |

## slot

| name | 说明 |
| :--- | :--- |


## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |


## Usage

```
<template>
    <div class="wx-demo">
        <div class="icon-list">
            <div class="icon-cell" v-for="icon in icons">
                <wx-icon
                    :name="icon"
                    :styles="{'font-size':'52px', 'color':'#4d4d4d'}">
                </wx-icon>
                <text>&nbsp;{{icon}}</text>
            </div>
        </div>
    </div>
</template>
<style type="text/css">
    .wx-demo {
        margin-top: 100px;
    }
    .icon-list {
        display: flex;

        flex-direction: row;
    }
    .icon-cell {
        flex: 1;
        align-items: center;
        justify-content: center;
        margin-bottom: 20px;
    }
</style>
<script>
    import { WxIcon } from 'weex-droplet-ui';

    export default {
        components: { WxIcon },

        data () {
            return {
                icons: [
                    'success',
                    'search',
                    'roundclose',
                    'enter',
                    'back',
                ]
            }
        },

        created () {

        },

        methods: {

        }
    }
</script>
```



