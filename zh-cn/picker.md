# picker

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| visible |  | Boolean |  | false |
| data | 数据格式参考demo | object |  | {} |

## slot

| name | 说明 |
| :--- | :--- |


## event

| 事件名 | 说明 | 回调参数 |
| :--- | :--- | :--- |
| wxChange | 选中的值 | item data |

## Usage

```
<template>
    <div class="wx-demo">
        <wx-popup 
            :visible="visible" 
            position="bottom" 
            :hasOverley="true"
            height="488px"
            ref="wxPopup"
            @wxChange="handleBottom">
            <div>
                <div class="btn-wrap">
                    <text class="btn" @click="handleCancel">取消</text>
                    <text class="btn" @click="handleFinish">完成</text>
                </div>
                <wx-picker :data="data" :visible="visible" @wxChange="handleChange"></wx-picker>
            </div>
        </wx-popup>

        <wx-button 
            height="80px"
            width="450px"
            borderRadius="200px"
            textColor="#fff"
            textFontSize="32px"
            @wxClick="visible=true">点击选择</wx-button>
        <text style="font-size:32px;">选中的值为：{{ selectedData.name }}</text>
    </div>
</template>
<style scoped>
    .wx-demo {

    }

    .btn-wrap {
        background-color: #ccc;
        height: 88px;
        font-size: 38px;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }

    .btn {
        line-height: 88px;
        height: 88px;
        width: 100px;
        text-align: center;
        color: #007aff;
        font-size: 32px;
    }
</style>
<script>
    import { WxPicker, WxButton, WxPopup } from 'weex-droplet-ui';
    import { PICKER_DATA } from './data';
    
    const PICKER_DATA = {
        list: [
            { name: '李娜', value: 0 },
            { name: '丁超', value: 1 },
            { name: '江武', value: 2 },
            { name: '尹士鹏', value: 3 },
            { name: '周灰灰', value: 4 },
            { name: '杨泉', value: 5 },
            { name: '厚本金融公司', value: 6 },
            { name: '揽胜', value: 7 },
            { name: '陆地巡洋舰', value: 8 },
            { name: '航空母舰', value: 9 },
            { name: '天宫一号', value: 10 },
            { name: '红岸工程', value: 11 },
        ],
        defaultValue: { name: '厚本金融公司', value: 6 },
        displayValue (item) {
            return item.name;
        }
    };

    export default {
        data () {
            return {
                data: PICKER_DATA,
                visible: false,
                selectedData: PICKER_DATA.defaultValue,
            }
        },

        created () {
        },

        methods: {
            handleBottom (visible) {
                this.visible = visible;
            },

            handleChange (data) {
                this.selectedData = data;
            },

            handleCancel () {
                this.$refs.wxPopup.hide();
            },

            handleFinish () {
                this.$refs.wxPopup.hide();
            },
        },
        components: { WxPicker, WxButton, WxPopup }
    }
</script>

```



