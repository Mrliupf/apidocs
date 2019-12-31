## 交易单详情
	参数：
		action：tradedetail
		userid 用户id
		tradeno 交易单号
		startdate 开始时间
		enddate 结束时间

## 翻译
	参数：
		action:translator
		userid 用户id
		content 要翻译的内容
		from 原文语言   //默认 en
		tos  要翻译成的语言  数组
			中文（zh-CHS），乌克兰语（uk），俄语（ru）
		 	越南语（vi），西班牙语（es）, 葡萄牙语(pt), 英语（en）

## 各国家进出口默认查询时间
	参数：
		action:tradecountrydate
		userid 用户id
		
## 获取供应商或采购商的联系人信息
	参数：
		action：tradedetailcontacter
		userid 用户id
		country 国家code
		companyid 公司id
		type  查询联系人   1 参考联系人，0 自带联系人
