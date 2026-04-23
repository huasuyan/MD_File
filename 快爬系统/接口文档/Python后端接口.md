---
created: 2026-04-21T15:19:57+08:00
modified: 2026-04-21T15:21:26+08:00
---
# python后端接口设计

## 数据爬取接口设计

**基础路径**：`/api/python/crawler`

|   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|
|接口名|接口地址|输入|输入示例|输出|输出示例|请求方式|备注|
|综合爬取数据|runIntegration|Object<br><br>任务id：<br><br>task_id<br><br>任务模式：<br><br>task_way：report/alert（字符串）<br><br>筛选时间：<br><br>filter_time: "datetime"<br><br>  <br><br>  <br><br>  <br><br>（params要求：<br><br>sources:['综合'、'社会']<br><br>page：1<br><br>）|Object<br><br>{<br><br>  "task_id": 1,<br><br>  "task_way":"report",<br><br>  "filter_time":"2026-04-22 20:51:16"<br><br>}|Object<br><br>状态代码：code<br><br>状态消息：msg<br><br>返回数据：data|{<br><br>"code": 1,<br><br>"msg": "success",<br><br>"data":null<br><br>}|POST||

## 舆情报告接口设计

**基础路径**：`/api/python/report`

|   |   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|---|
|接口名|接口地址|输入|输入示例|输出|输出示例|请求方式|备注|
|生成舆情报告|`/generateReport`|`special_report_id`：报告专题ID|special_report_id：1|Object<br><br>状态代码：code<br><br>状态消息：msg<br><br>返回数据：data|Object<br><br>{<br><br>"code": 1,<br><br>"msg": "success",<br><br>"data": Object(report_result)<br><br>}|GET||