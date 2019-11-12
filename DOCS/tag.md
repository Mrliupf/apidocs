
## 用户标签列表
	参数：
		action:usertaglist
		userid 用户id
		pageindex  页码
		pagesize   每页显示数量
		
## 标签详情
	参数：
		action:usertagdetaillist
		userid 用户id
		pageindex  页码
		pagesize   每页显示数量
		keyword    搜索词
		tagid     标签id

## 添加标签
	参数：
		action:useraddtags
		userid 用户id
		tagname 标签名称
		tagids 已存在标签id
		noteid 当前公司id

## 删除标签
	参数：
		action:userdeletetags
		userid 用户id
		tagid  标签id

## 更改收藏公司备注
	参数：
		action:useraddremark
		noteid 收藏id
		remark 备注
		userid 用户id+“”

## 取消收藏
	参数：
		action:usercancelcollection
		noteid 收藏id
		userid 用户id

## 添加收藏公司
	参数：
		action:useraddcompany
		userid 用户id
		tagid 当前标签id
		companyname 公司名称
		country 所属国家
		companyaddress 公司地址
		telphone 电话
		website 网址

## 修改收藏公司信息
	参数：
		action:userupdatecompany
		userid 用户id
		noteid 收藏id
		companyid 公司id
		country 所属国家
		companyaddress 公司地址
		telphone 电话
		website 网址

## 获取标签下公司联系人列表
	参数：
		action:usertagdetailcompanycontactlist
		userid 用户id
		countrycode 国家编码
		companyid 公司id

## 删除标签下公司联系人
	参数：
		action:usercompanycontactdelete
		userid 用户id
		countrycode 国家编码
		companyid 公司id
		contactid 联系人id

## 更新标签下公司联系人
	参数：
		action:usercompanycontactupdate   添加修改公用此接口
		userid 用户id
		countrycode 国家编码
		companyid 公司id
		contactid 联系人id   添加联系人时此参数为空
		name 联系人
		email 邮箱
		title 职称
		telephone 联系方式