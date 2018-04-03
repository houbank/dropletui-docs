# indexList

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| items | 数据 | array |  | \[\] |
| wxChange | 回调函数 | function |  | - |

## slot

| name | 说明 |
| :--- | :--- |


## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |
| wxChange |  | 选中的项数据 |

## Usage

```
<template>
    <div class="wx-demo">
        <wx-indexlist 
            :items="getData()" 
            @wxChange="handleChange">
        </wx-indexlist>
    </div>
</template>
<script>
    import { WxIndexlist } from 'weex-droplet-ui';
    const modal = weex.requireModule('modal');
    export default {
        components: {
            WxIndexlist
        },

        data () {
            return {

            }
        },

        methods: {
            handleChange (item) {
                console.log(item);
            },

            getData () {
                let list=[];
                for(let i= 0; i < 26; i++){
                    list.push({
                        text: String.fromCharCode(65+i),
                        list: [
                            {
                                text:String.fromCharCode(65+i)+1
                            },{
                                text:String.fromCharCode(65+i)+2
                            },{
                                text:String.fromCharCode(65+i)+3
                            },{
                                text:String.fromCharCode(65+i)+4
                            }
                        ]
                    });
                }
                console.log(list);
                return list; 
            },
        }
    };
</script>
```



