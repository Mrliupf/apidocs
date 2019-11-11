## api 
	测试地址：http://192.168.1.118/api/xm/execobj

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












