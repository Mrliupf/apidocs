## 字段解释
		0: "name"  国家名字
		1: "source"  数据源
		2: "inout"  进出口
		3: "time"   时间
		4: "class"   下划线类
		5: "fanyi"    是否有翻译
		6: "shipmentport"  起运港
		7: "uploadport"    卸载港
		8: "billno"        提单号   
		9: "notifyname"    通知人名称
		10: "hscode"       hs 编码
		11: "buyername"     采购商
		12: "suppliername"   供应商
		13: "prodesc"         描述
		14: "origincountry"    原产国
		15: "preciselyquery"   精确查询  指定查询供应商（supplier）或采购商（buyer）
		16: "marksnumbers"      唛头
		17: "container"           集装箱号
		18: "destinationcountry"    目的国
		19: "lang"                   翻译成什么语言
		20: "brand"                  品牌名称  
		21: "manufacturer"          制造商
		22: "salecountry"      出口国
		23: "customs"          关区

## 国家列表
	参数：
		action:tradecountry
		userid 用户id	

## 高级搜索 
	参数：
		action:tradesearch
		userid 用户id
		country 国家编码
		inout   进出口  进口（import）/出口(export)
		startdate 开始时间
		enddate  结束时间
		billno 提单号
		notifyname  通知人
		hscode hs编码
		buyername 采购商
		suppliername 供应商
		prodesc 商品描述
		origincountry 原产国
		preciselyquery 精确查找 采购商(buyer)/供应商(supplier)
		marksnumbers 唛头
		container 集装箱号
		destinationcountry 目的国
		brand  品牌名称
		manufacturer 制造商
		salecountry 出口国
		customs 关区
		filterword 筛选
		pageindex 页码
		pagesize 每页显示数据

		tabname 情报分析（analy）/总量（total）/供应商（supplier）/采购商(buyer)

## 搜采购商
	参数：
		action:tradebuyersearch
		userid 用户id
		searchtype 搜索类型 公司（buyername）/产品（productdetail）/新增采购商（buyernew）/地址（buyeraddress）
		country 国家编码
		inout 进出口 进口（import）/出口（export）
		keyword 搜索词
		startdate 开始时间
		enddate 结束时间
		pageindex 页码
		pagesize 每页显示数量
		sortcolumn 排序列
						tradecount 次数
						tradetatalcount 总次数
						tradecountpercent 百分比
						tradecountry 国家数量
						tradepartner 交易伙伴数量
						money 金额
						weight 重量
						number 数量
		sorttype 排序方式  升序（asc）/降序（desc）
		filterword 筛选词

## 公司合并
	参数：
		action:tradecompanymerge
 



