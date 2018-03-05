# Validator-wxp

一款小巧无依赖的表单验证库，支持独立字符串验证。

#### 怎么使用？

步骤1:

- 安装 npm install validator-wxp —save  或 直接script标签引入

步骤2:

- 独立字符串验证

  ```javascript
  // just for string
  import Validator from 'validator-wxp'
  var v = new Validator()
  v.isPhone('sss') // false
  ```

- 表单验证

  ```javascript
  import Validator from 'validator-wxp'
  var v = new Validator('form_name',[
      name:"alphanumeric", // form内部表单元素name
  	display:"字数小于5个字符|大于15个字符", // 错误提示
      rules: 'min_length(5)|max_length(15)' // 需要的规则
  ],function(evt, obj){
      // if get error--> obj.errors.length>0
    	// 你所需要的dom操作，如显示在什么元素内，页面滚动等
  })
  // 支持onblur等事件调用验证函数 blurValidate()
  function blurValidate(){
  	v.validate()
  }
  ```

  ​


### 独立字符串验证

```JavaScript
var v = new Validator();
v.isEmail('wowohoo@qq.com'); // -> 验证合法邮箱  |=> 返回布尔值
v.isIp('192.168.23.3'); // -> 验证合法 ip 地址  |=> 返回布尔值
v.isFax(''); // -> 验证传真  |=> 返回布尔值
v.isPhone('13622667263'); // -> 验证手机  |=> 返回布尔值
v.isTel('021－324234-234'); // -> 验证座机  |=> 返回布尔值
v.isUrl('http://JSLite.io'); // -> 验证URL  |=> 返回布尔值
v.maxLength('JSLite',12); // -> 最大长度  |=> 返回布尔值
v.minLength('JSLite',3); // -> 最小长度  |=> 返回布尔值
v.required('23'); // -> 是否为必填(是否为空)  |=> 返回布尔值
```





##### 参考

- https://github.com/jaywcjlove/validator.js /轻量级的JavaScript表单验证，字符串验证。没有依赖，支持UMD，~3kb

