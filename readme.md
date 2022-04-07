
szy 工作日加班统计

## TODO

加班到次日凌晨的统计暂未实现

## 考勤记录

1. 打开 OA 系统 - 考勤日历页面 http://oa.szy.cn/sys/portal/page.jsp?j_module=true#j_start=%2Fsys%2Fattend%2Findex.
jsp&j_target=_iframe&j_path=%2FattendCalendar 
2. 通过切换月份可获取到原始考勤记录的请求
3. 控制台运行以下代码
```js
fetch("http://oa.szy.cn/sys/attend/sys_attend_main/sysAttendMain.do?method=mycalendar&categoryType=attend&fdStart=2021-01-01+00%3A00&fdEnd=2022-12-31+00%3A00&s_ajax=true", {
    "headers": {
        "accept": "text/plain, */*; q=0.01",
        "accept-language": "en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7,ru;q=0.6",
        "x-requested-with": "XMLHttpRequest"
    },
    "referrer": "http://oa.szy.cn/sys/attend/index.jsp?&j_iframe=true",
    "referrerPolicy": "strict-origin-when-cross-origin",
    "body": null,
    "method": "GET",
    "mode": "cors",
    "credentials": "include"
});
```
4. 切换到 network, 保存该请求的响应体到 `考勤统计.json`

