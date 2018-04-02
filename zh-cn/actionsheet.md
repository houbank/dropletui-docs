# actionsheet

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| v-model |  | boolean |  | false |
| closeOnClickMask | 点击背景隐藏 | boolean |  | true |
| cancelText | 取消 | string |  | 取消 |
| titleText | 标题 | string |  | 标题 |
| actions | 内容主题 | array |  | 空数组 |
| actionColor | string | string |  | \#0076FF |
| cancelColor | 取消文字颜色 | string |  | \#0076FF |
| actionFontSize | 内容文字大小 | string |  | 40px |
| cancelFontSize | 取消文字大小 | string |  | 40px |

## Usage

```
<template>
    <div>
        <wx-button width="600px" textFontSize="32px" class="button"
         @wxClick="showSheet1 = true">不带取消按钮</wx-button>

        <wx-button width="600px" textFontSize="32px" class="button"
          @wxClick="showSheet2 = true">点击空白处不关闭</wx-button>

        <wx-actionsheet
            v-model="showSheet1"
            :actions="actions1"
            :pos="{top: '0px', bottom: '0px'}"
            cancelText=""
            titleText=""
            actionColor="#f00"
            actionFontSize="52px">
        </wx-actionsheet>

        <wx-actionsheet
            v-model="showSheet2"
            :actions="actions2"
            :closeOnClickMask="false"
            titleText="客服服务时间:工作日09:00-20:00"
            cancelColor="#f00"
            cancelFontSize="38px">
        </wx-actionsheet>
    </div>
</template>

<script>
    import { WxActionsheet, WxButton } from 'weex-droplet-ui';
    const modal = weex.requireModule('modal');

    export default {
        components: {
            WxActionsheet,
            WxButton
        },

        data () {
            return {
                showSheet1: false,
                showSheet2: false,
                actions1: [],
                actions2: []
            }
        },

        methods: {
            takePhoto () {
                modal.toast({ message: 'taking photo' });
            },

            openAlbum () {
                modal.toast({ message: 'opening album' });
            },

            callPhone (action) {
                modal.toast({ message: action.name });
            },

            takeMobile (action) {
                modal.toast({ message: action.name });
            }
        },

        mounted () {
            this.actions1 = [
                {
                    name: '拍照',
                    method: this.takePhoto
                },
                {
                    name: '从相册中选择',
                    method: this.openAlbum
                },
            ];

            this.actions2 = [
                {
                    name: '咨询服务热线:400-888-8888',
                    method: this.callPhone
                },
                {
                    name: '152-2926-7590',
                    method: this.takeMobile
                }
            ];
        }
    };
</script>
<style type="text/css">
    .button {
        margin-top: 100px;
        margin-left: 75px;
    }
</style>
```



