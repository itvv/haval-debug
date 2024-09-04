# haval-debug
哈弗大狗调试模式安装指南
## 手机搭配笔记本电脑做本地代理配置安装调试模式apk

### 下载仓库代码

```
git clone https://github.com/itvv/haval-debug.git
```
### 修改nginx-config
#### 路径：haval-debug/nginx-1.26.2/conf/nginx.conf
主要修改root和证书目录

```
# root
root C:/Users/Haval/Desktop/haval-debug/html;

# 证书
ssl_certificate    C:/Users/Haval/Desktop/haval-debug/cert/fullchain.pem;
ssl_certificate_key    C:/Users/Haval/Desktop/haval-debug/cert/privkey.pem;

```
修改```C:/Users/Haval/Desktop``` 为仓库下载所在位置

### 运行nginx
详见[windows系统下安装配置nginx](https://www.jianshu.com/p/f8cad88c5e64)

### Start
手机开热点，电脑连接，然后查找当前电脑ipv4地址（不会的自行百度），配置host，在最后增加一行（当前电脑的ipv4地址	dzsms.gwm.com.cn），例```192.168.110.101	dzsms.gwm.com.cn```，访问[地址](https://dzsms.gwm.com.cn/apiv2/car_apk_update)测试能否获取到json
```
{
	"code": 200,
	"message": "查询成功",
	"data": {
		"apk_version": "3.1",
		"apk_url": "https://dzsms.gwm.com.cn/apk/app_debug_mode_v_3.1.apk",
		"apk_msg": "恭喜成功",
		"isUpdate": "Yes",
		"apk_forceUpdate": "Yes",
		"notice": {
			"vin_notice": [
				"VIN码可以在仪表板左上方（前风挡玻璃后面）和车辆铭牌上获得。",
				"本应用适用于2019年及之后生产的车型。"
			],
			"add_notice": [
				"制造年月可通过车辆铭牌获得。",
				"本应用适用于2019年及之后生产的车型。"
			]
		},
		"notice_en": {
			"vin_notice": [],
			"add_notice": [
				"The date can be obtained from the certification label."
			]
		}
	}
}
```
### Step
电脑开热点（不会的自行百度），车机连接，注意车机暂时关闭数据流量，然后点击智能手册安装即可

### End

### Thank
借鉴：[WangXiaopai595/haval](https://github.com/WangXiaopai595/haval)  [kinghisky/hafu](https://github.com/kinghisky/hafu)  [哈弗益达](https://www.douyin.com/hashtag/1749020233142279)