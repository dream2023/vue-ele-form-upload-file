# vue-ele-form-upload-file | vue-ele-form 的文件上传扩展组件

[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg)](https://opensource.org/licenses/mit-license.php)
[![npm](https://img.shields.io/npm/v/vue-ele-form-upload-file.svg)](https://www.npmjs.com/package/vue-ele-form-upload-file)
[![download](https://img.shields.io/npm/dw/vue-ele-form-upload-file.svg)](https://npmcharts.com/compare/vue-ele-form-upload-file?minimal=true)

## 介绍

vue-ele-form-upload-file 做为 vue-ele-form 的第三方扩展, 通过对 [vue-ele-upload-file](https://github.com/dream2023/vue-ele-upload-file) 的封装, 使得上传更加方便和容易

![image](https://raw.githubusercontent.com/dream2023/images/master/vue-ele-form-upload-file.0kas121tsegl.gif)

## 安装

```bash
npm install vue-ele-form-upload-file --save
```

## 使用

```js
import EleForm from 'vue-ele-form'
import EleFormUploadFile from 'vue-ele-form-upload-file'

// 注册 upload-file 组件
Vue.component('upload-file', EleFormUploadFile)

// 注册 ele-form
Vue.use(EleForm, {
  // 可以在这里设置全局的 upload-file 属性
  'upload-file': {
    action: 'https://jsonplaceholder.typicode.com/posts' // 上传地址
  }
})
```

```js
formDesc: {
  xxx: {
    label: 'xxx',
    type: 'upload-file', // 只需要在这里指定为 upload-file 即可
    // 属性参考: https://github.com/dream2023/vue-ele-upload-file
    attrs: {
      // 上传地址
      action: 'https://jsonplaceholder.typicode.com/posts',
      isCanDelete: false,
      // 上传后对响应处理, 拼接为一个URL地址
      handleResponse(response, file) {
        // 根据响应结果, 设置 URL
        return {
          name: file.name,
          url: 'https://xxx.com/file/' + response.path, // 示例而已
          size: file.size
        }
      }
    }
  }
}
```

## 相关链接

- [vue-ele-upload-file](https://github.com/dream2023/vue-ele-upload-file)
- [vue-ele-form](https://github.com/dream2023/vue-ele-form)
- [element-ui](http://element-cn.eleme.io)
