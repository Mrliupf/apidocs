## 产品搜/一键搜 搜索
	参数:
		action:productsearch
		userid 用户id
		product 产品描述
		hscode hs编码  至少四位数
		languagesarry  翻译后语言  数组
		condition 或/与   或：0 与：1
		startdate 开始时间
		enddate 结束时间
		pageindex 页码
		pagesize 每页显示数量
		filterword 筛选词
		sortcolumn 排序列    采购商数量（buyer）/供应商数量(supplier)
		sorttype 排序方式  升序(asc)/降序(desc)

## 点击采购商/供应商数字
	参数:
		action:producttradenumberdetail
		userid 用户id
		product 产品描述
		hscode hs编码  至少四位数
		languagesarry  翻译后语言  数组
		condition 或/与   或：0 与：1
		startdate 开始时间
		enddate 结束时间
		pageindex 页码
		pagesize 每页显示数量
		filterword 筛选词
		sortcolumn 排序列    
						进口频次(tradecount)
						进口总次数(tradetotalcount)
						产品进口率(tradecountpercent)
						贸易国家数(tradecountrycount)
						贸易伙伴数(tradepartnercount)
		sorttype 排序方式  升序(asc)/降序(desc)

		country 国家code
		tradetype 点击的是供应商(supplier) 还是采购商（buyer）

## 点击贸易商查看
	参数：
		action:producttrades
		userid 用户id
		product 产品描述
		hscode hs编码  至少四位数
		languagesarry  翻译后语言  数组
		condition 或/与   或：0 与：1
		startdate 开始时间
		enddate 结束时间
		pageindex 页码
		pagesize 每页显示数量
		filterword 筛选词
		country 国家code

## 公司详情数据
	参数:
		action:producttradecompanydetail
		userid 用户id
		product 产品描述
		hscode hs编码  至少四位数
		languagesarry  翻译后语言  数组
		condition 或/与   或：0 与：1
		startdate 开始时间
		enddate 结束时间
		pageindex 页码
		pagesize 每页显示数量
		tradetype 点击的是供应商(supplier) 还是采购商（buyer）
		filterword 筛选词
		country 国家code

		companyid 公司id
		detailtype 点击的那个列 
					频次（tradecount)
					贸易国家（tradecountry）
					贸易搜伙伴（tradepartner）
		searchcolumn 按字段搜索 搜公司（ companyname）

