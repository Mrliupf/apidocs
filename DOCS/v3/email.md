## 联系人组列表
	参数：
		action:emailgrouplist
		userid 用户id
		pageindex 页码
		pagesize 每页显示数量

## 联系人组添加
	参数：
		action:emailgroupadd
		userid 用户id
		name 组名称

## 联系人组修改
	参数：
		action:emailgroupupdate
		userid 用户id
		groupid 组id
		name 组名称
		note 备注


##	联系人组合并
	参数：
		action:emailgroupmerge
		userid 用户id
		groupids 选中的合并项，数组

## 联系人组删除
	参数：
		action:emailgroupdelete
		userid 用户id
		groupids 选中的合并项，数组

## 联系人组验证
	参数：
		action:emailverify
		userid 用户id
		groupid 组id

## 联系人组excel上传    api/xm/Upload
	参数类型：  form-data
		userid 用户id
		groupid 联系人组id


## 联系人列表
	参数：
		action:emailcontactslist
		userid 用户id
		groupid 选择的组id
		emailkeyword 邮箱查询关键字
		verifystatus 邮箱状态  有效（1）/无效（-1）
		pageindex 页码
		pagesize 每页显示数量

## 联系人列表更新邮箱状态
	参数：
		action:emailcontactsupdateverifystatus
		userid 用户id
		contactid 联系人id
		verifystatus 状态 有效（1）/无效（-1）/待验证（0）

## 联系人列表更新联系人信息
	参数：
		action:emailcontactsupdateinfo
		userid 用户id
		contactid 联系人id
		name 名称
		company 公司
		area 地区
		industry 行业
		email 邮箱
		phone 电话

## 联系人列表批量添加分类
	参数：
		action:emailcontactsaddtogroup
		userid 用户id
		groupid 组id
		contactids 选中的联系人id，数组

## 联系人列表批量删除联系人
	参数：
		action:emailcontactsdelete
		userid 用户id
		contactids 联系人id，数组

## 联系人列表邮件模板添加
	参数：
		action:emailcontactstemplateadd
		userid 用户id
		lablelname 标签
		subject 主题
		content 内容

## 联系人列表邮件模板删除
	参数：
		action:emailcontactstemplatedelete
		userid 用户id
		tpid 邮件模板id

## 联系人列表邮件模板列表
	参数：
		action:emailcontactstemplatelist
		userid 用户id

