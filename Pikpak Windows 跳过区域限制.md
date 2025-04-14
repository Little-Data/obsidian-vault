# (版本 V2.5.6.4831)(可能适用于以后版本)
打开 `Pikpak\resources\app\out\main-renderer\main.xxxxxxxx.js` (xxxxxxxx为随机二进制数，如b9ceb61b)
找到下面的数据：
```js
(`https://access.${e}/access_controller/v1/area_accessible`,{withCredentials:!1,withCaptcha:!1})
```
删除后保存即可。