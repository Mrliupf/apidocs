## 获取询盘列表
	参数：
		action:cloudguestinformationrecommending
		userid 用户id		 	
		pageindex 页码
		pagesize 每页显示条数

## 修改询盘列表状态
	参数：
		action:cloudguestmodificationlist
		userid 用户id
		page_id 询盘主页id
		state 状态  2已屏蔽  0未屏蔽 

## 获取关键词列表
	参数：
		action:cloudguestkeywordlist
		userid 用户id

## 添加关键词
	参数：
		action:cloudguestkeywordadd
		userid 用户id
		keyword 关键词

## 删除关键词
	参数：
		action:cloudguestkeyworddel
		userid 用户id
		keywordid 关键词id

## fackbook账户授权url
	参数：
		action:cloudguestgeturl
		userid 用户id
		account_type 账号类型

## 获取已授权账号
	参数：
		action:cloudguestgetboundaccount
		userid 用户id
