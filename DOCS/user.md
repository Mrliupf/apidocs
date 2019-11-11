## api 测试地址：http://192.168.1.118/api/xm/execobj
## 登录
    参数：
		action:login
		username 用户名  17701759687
		password 密码    qqqq1111
		source   来源

## 用户基本信息
	参数：
		action:userinfo
		userid 用户id

## 修改密码
	参数：
		action:userupdatepwd
		userid 用户id
		password 旧密码
		newpassword 新密码

## 获取子账户信息
	参数：
		action:userchilddetail
		userid 用户id
		childuserid 子账号id

## 修改/添加子账号信息
	参数：
		action:userchildupdate
		userid 用户id
		childuserid 子账号id
		username 账号
	 	email 邮箱
	 	countrys 选择的国家
	 	module 选择的模块
	 	password 密码

## 删除子账户
	参数：
		action:userchilddelete
		userid 用户id
		childuserid 子账号id

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
		userid 用户id

## 取消收藏
	参数：
		action:usercancelcollection
		noteid 收藏id
		userid 用户id

## 添加自定义收藏公司
	参数：
		action:useraddcompany
		companyid 当前公司id
		companyname 公司名称
		country 所属国家
		companyaddress 公司地址
		telphone 电话
		website 网址
		userid 用户id

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









