## 太原理工大学空闲教室查询

> 更新了2018-2019年度第二学期课表 
> 2019.3.10

### Demo

[预览](https://risid.github.io/freeclassroom/)

与之配对的Java程序以后放出
每个学期需要重新生成课表信息的json文件

### 请求格式

请求: /{校区id}/{周次}.json
意味着需要为每个校区建立一个文件夹

### Json文件

#### main.json

| 参数 | 备注               |
| ---- | ------------------ |
| s    | 学期开始的时间     |
| c    | 校区 |
| b    | 教室归属映射       |
| t    | 教室种类映射       |

#### {周次}.json

| 参数 | 备注               |
| ---- | ------------------ |
| w   | 周次     |
| b    | 教学楼 |

#### 数组

```
// 教学楼号
{"108":
    [
        // 教室信息
        // 1. 教室名
        // 2. 容量
        // 3. 类型
        ["8101",72,0],
        // 下面7个数组，从0开始到7分别对应星期日到星期六的空闲小节
        // 如0,1则说明第一小节和第二小节是空课，最多11小节
        [0,1,2,3,4,5,6,7,8,9,10],
        [3,6,7,8,9,10],[6,7],
        [4,5,6,7,10],[8,9,10],
        [8,9,10],
        [0,1,2,3,4,5,6,7,8,9,10],
        // 下一个教室
        ["8102",72,0],
...
    ]
}
```



### 支持的教室

```
"明向校区": {
    "801": "行知楼",
    "803": "行逸楼",
    "804": "行思楼",
    "807": "行远楼",
    "818": "行勉楼"
},
"迎西校区": {
    "101": "思贤楼",
    "102": "机械馆",
    "103": "电机馆",
    "105": "逸夫楼",
    "106": "化工馆",
    "108": "思韵楼"
},
"虎峪校区": {
    "201": "致明楼",
    "206": "致远楼"
}
```
