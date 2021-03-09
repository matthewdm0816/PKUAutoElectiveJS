## AutoElectiveChan

### Introduction
AutoElectiveChan是一个帮助你选课的GreaseMonkey脚本. 提供了选课列表, 验证码自动推送和接受, 自动检测刷新和自动登录功能.

### How to use
1. 安装浏览器对应的油猴脚本插件:
    - Chrome: Tampermonkey 或 Violentmonkey
    - Firefox: Greasemonkey、Tampermonkey 或 Violentmonkey
    - Safari: Tampermonkey 或 Userscripts
    - Microsoft Edge: Tampermonkey
    - [Further Docs Here](https://greasyfork.org/zh-CN)

2. 新建脚本, 并且复制autoelective.js的内容, 保存. 你可能需要授予一些权限给本脚本.
3. 修改你的student_id, password, sc_key, server_url.
    ```javascript
    var student_name = "九条可怜"
    var student_id = 1987654321;
    var password = "1987654321";
    var send_key = 'SCT..............................';
    let server_url = "https://example.com/example.txt";
    ```
    - student_id, password: 你的PKU IAAA帐号和密码
    - sc_key是你的Server酱推送服务API Key
    - server_url是在线获取验证码的url, 你会想在这里放上能够人工修改的验证码文本. 一个简单的方法是使用简单的PHP脚本来修改和返回验证码. 然后还可以利用WebHook服务(推送服务提供)来使用图形化界面推送验证码.
4. 修改你的CourseNames, CIDs为数组, 且元素按顺序分别为课程名和对应课程班号:
    ```javascript
    var CourseNames = [
        '日本经济',
        '汉字太极与养生课',
        '汉字太极与养生课',
        '汉字太极与养生课',
    ];
    var CIDs = [
        1,  // 对应'日本经济'
        1, 2, 3     // 对应'汉字太极与养生课'
    ];
    ```
5. 关于如何使用推送服务,请参考[Server酱](https://sct.ftqq.com/)