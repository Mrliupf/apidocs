## 社媒云搜
	参数：
		action:mediasearch
		userid 用户id
		keyword 搜索词
		pageindex 页码
		pagesize 每页显示条数
		deepid 搜索deepid
		type 类型 默认all  all/fb-pages/linkedin/twitter 
		filterkeyword 过滤关键词

## 追踪
	参数：
		action:mediasearchtrace
		userid 用户id
		idarray 社媒云搜结果id集合

## 搜索日志
	参数：
		action:mediasearchhistory
		userid 用户id
		pageindex 页码
		pagesize 每页显示条数

## 历史搜素日志删除
	参数：
		action:mediasearchhistorydelete
		userid 用户id
		deepid 日志deepid

## 过滤关键词列表
	参数：
		action:mediasearchfilterlist
		userid 用户id

## 过滤关键词添加
	参数：
		action:mediasearchfilteradd
		userid 用户id
		filterword 过滤词

## 过滤关键词删除
	参数：
		action:mediasearchfilterdelete
		userid 用户id
		filterid 过滤词id

## 公司详情页
	参数:
		action:mediasearchcompanydetail
		userid 用户id
		searchid 搜索结果id
		employeekeyword 员工信息
		pageindex 	页码
		pagesize 每页显示条数

## 发送邮件
	参数：
		action:mediasendemail
		userid 用户id
		mailto 收件人
		subject 标题
		body 内容

## 社媒搜详情收藏
	参数：
		action:medianotecollect
		userid 用户id
		companyid 公司id
		searchid 搜索结果id

	 





