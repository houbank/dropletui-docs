# button 说明文档

## Attributes

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| width |  | string |  | 670px |
| height |  | string |  | 90px |
| borderRadius |  | string |  | 12px |
| disabled |  | boolean |  | false |
| styles | 常规css样式 | object |  | {} |
| textColor | 文本颜色 | string |  | \#fff |
| textFontSize | 字体大小 | string |  | 36px |
| disableOnPromise | 点击按钮disable on promise | function |  |  |
| disabledBgColor | disabled时按钮背景颜色 | string | 常规background-color值 | rgba\(0, 0, 0, 0.1\) |

## slot

| name | 说明 |
| :--- | :--- |
| 空 | button内容 |

## Usage

```
<template>
    <div class="wx-demo">
        <wx-button 
          height="80px"
          width="450px"
          borderRadius="200px"
          textColor="#fff"
          textFontSize="32px"
          :disabled="disabled"
          @wxClick="wxClickHandle1">normal button</wx-button>

        <wx-button 
            height="80px"
            width="450px"
            borderRadius="200px"
            textColor="#fff"
            textFontSize="32px"
            :disabled="false"
            :styles="{'margin-left': '50px','margin-top': '80px', 'background-color': '#F37B1D',}"
            disabledBgColor="#e5e5e5"
            :disableOnPromise="wxClickHandle2">promise button</wx-button>
    </div>
</template>

<script>
    import { WxButton } from '../../index';
    const modal = weex.requireModule('modal');
    export default {
        data(){
            return {
                disabled: true
            }
        },
      components: {
          WxButton 
      },
      mounted () {
          setTimeout(()=> {
              this.disabled = false
          }, 2000)
      },
      methods: {
          wxClickHandle1 () {
              modal.toast({
                  message: 'clicked 1'
              });
          },

          /**
           * 1. 点击按钮，会执行wxClickHandle2()方法，且必须返回Promise。
           * 2. 解决避免在请求未结束时产生重复提交或请求
           * 3. 无论结果是resolve或者reject，button都会恢复至可点击状态。
           * @return {Promise} promise
           */
          wxClickHandle2 () {
              modal.toast({
                  message: 'clicked 2'
              });
              return this.request().then((data) => {
                  // TODO
                  console.log(data)
              }).catch((data) => {
                  // TODO
                  console.log(data)
              })
          },

          /**
           * 模拟Promise封装接口请求方法，必须返回Promise
           * @return {Promise} promise
           */
          request () {
              return new Promise(function(resolve, reject) {
                  const result1 = '接口调用成功';
                  const result2 = '接口调用失败';
                  setTimeout(() => {
                      if (true) {
                          resolve(result1);
                      } else {
                          reject(result2);
                      }
                  }, 2000);
              });
          },
        }
    }
</script>

```





