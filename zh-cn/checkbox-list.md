# checkbox-list

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| v-model | 参照demo | Array |  | 无 |
| width | 行宽 | string |  | 750px |
| height | 行高度 | string |  | 100px |
| padding | 距离左右侧px值 | string |  | 20px |
| checkedColor | 选中复选框颜色 | string |  | \#027FF3 |

## slot

| name | 说明 |
| :--- | :--- |


## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |
| wxChange |  | array item object |

## Usage

```
<template>
    <div class="wx-demo">
        <wx-checkbox-list 
            v-model="list" 
            width="750px"
            height="100px"
            padding="20px"
            checkedColor="red"
            @wxChange="handleChange">
        </wx-checkbox-list>
        <div class="result">
            <text v-for="item in list">{{ item.checked }},</text>
        </div>
    </div>
</template>
<style type="text/css" scoped>
    .wx-demo {
        flex-direction: column;
        align-items: center;
    }

    .result {
        flex-direction: row;
        justify-content: center;
        margin: 40px;
    }
</style>
<script>
    import { WxCheckboxList } from '../../index';
    export default {
        components: {
            WxCheckboxList,
        },
        data () {
            return {
                 list: [
                    { title: '爱看电影', value: 1, checked: false },
                    { title: '爱看小说', value: 2, checked: true },
                    { title: '爱看抖音', value: 3, checked: false },
                    { title: '爱刷微博', value: 4, checked: true }
                 ]
            }
        },
        created () {

        },
        methods: {
            handleChange (list) {
                console.log(JSON.parse(JSON.stringify(list)))
            },
        }
    }
</script>
```



