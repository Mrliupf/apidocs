## api 
	测试地址：http://192.168.1.118/api/xm/execobj

## 注册
	参数：
		action:register
		phone 电话
		emial 邮箱
		password 密码
		companyname 公司名称
		contact 联系人
		cityid 城市id
		source 来源

## 忘记密码
	参数:
		action:userforgotpwd
		username 用户名
		email 用户默认邮箱


## 确认重置密码
	参数:
		action:userresetpwdbyemail
		username 用户名
        password 密码
        token  url中的token
        isurl 验证url地址是否有效，  验证url时 = 1 默认为空
 
## 登录
    参数：
		action:login
		username 用户名  
		password 密码    
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

## 邮箱配置展示
	参数:
		action:useremailshow
		userid 用户id
		

## 邮箱配置
	参数:
		action:useremailsetting
		userid 用户id
		contact 联系人
		email 邮箱
		emailpwd 邮箱密码
		smtp smtp服务器
		












