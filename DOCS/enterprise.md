## 企业搜索
	参数：
		action:enterprisesearch
		userid 用户id
		companynames 公司名称关键词
		product 产品关键词搜索
		hscode hs编码
		condition 或|与 对应 1：0
		startdate 开始时间
		enddate 结束时间 搜索时间不能超过三年
		pageindex 页码
		pagesize 每页显示条数

## 企业搜索收藏
	参数：
		action:enterprisecollect
		userid 用户id
		companyname 公司名称
		companyid 公司id
		companytype 公司类型
		country 国家编码

##	执行合并搜索
	参数：
		action:enterprisetradeanaly
		userid 用户id
		startdate 开始时间
		enddate 结束时间 搜索时间不能超过三年
		product 产品关键词搜索
		hscode hs编码
		condition 或|与 对应 1：0
		companyidarray 公司id数组
		pagesize 每页显示条数

## 执行合并搜索缓存请求接口
	参数:
		action:enterprisetradeanalywithpage
		userid 用户id
		tradetype  国家分析（country）/伙伴分析（partner）/产品分析（product）/年度贸易（year）/交易圈（tradecircly）
		startdate 开始时间
		enddate 结束时间 搜索时间不能超过三年
		product 产品关键词搜索
		hscode hs编码
		condition 或|与 对应 1：0
		companyidarray 公司id数组
		pageindex 页码
		pagesize 每页显示条数

## 交易伙伴交易详情
	参数：
		action:enterprisetradepartnerdetail
		userid 用户id
		startdate 开始时间
		enddate 结束时间 搜索时间不能超过三年
		product 产品关键词搜索
		hscode hs编码
		condition 或|与 对应 1：0
		companyidarray 公司id数组
		pageindex 页码
		pagesize 每页显示条数
		--以下是新加参数
		companyid 公司ip
		tradetype 进出口类型 export/import

## 交易产品详情
	参数:
		action:enterprisetradeproductdetail
		userid 用户id
		startdate 开始时间
		enddate 结束时间 搜索时间不能超过三年
		product 产品关键词搜索
		hscode hs编码
		condition 或|与 对应 1：0
		companyidarray 公司id数组
		pageindex 页码
		pagesize 每页显示条数
		--以下是新加参数
		tradetype 进出口类型 export/import
		hscodedetail 当前行具体的hs编码
		productdetail 当前行产品具体描述

## 交易产品交易国家详情
	参数:
		action:enterprisetradeproductcountrydetail
		userid 用户id
		startdate 开始时间
		enddate 结束时间 搜索时间不能超过三年
		product 产品关键词搜索
		hscode hs编码
		condition 或|与 对应 1：0
		companyidarray 公司id数组
		pageindex 页码
		pagesize 每页显示条数
		--以下是新加参数
		tradetype 进出口类型 export/import
		hscodedetail 当前行具体的hs编码
		productdetail 当前行产品具体描述		

## 每笔交易单详情
	参数:
		action:enterprisetradedetail
		userid 用户id
		startdate 开始时间
		enddate 结束时间 搜索时间不能超过三年
		product 产品关键词搜索
		hscode hs编码
		condition 或|与 对应 1：0
		companyidarray 公司id数组
		--以下是新加参数
		tradeno 交易号









