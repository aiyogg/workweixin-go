# workweixin-go
golang实现企业微信API
- 实现了部门相关api
- 实现了tag相关api
- 实现了获取用户相关api
- 实现发送聊天相关api
- 实现了手机号对应user转换

注意:因为企业微信不同的功能对应不同的应用，不同的应用agentId 和secert是不一样的，故调用api时候请按照官方说明调用对应方法即可
```
	var w work.WorkWeixin //声明企业微信  通讯录里面的secret
	w.Init("cropid", "secret", 0)

	var notify work.WorkWeixin //自己创建应用程式的对应的secret 和 agentId
	notify.Init("cropid", "secret", 1000008)

	//获取token
	//fmt.Println(w.GetAccessToken())
	//
	//fmt.Println(w.GetAccessToken())
	//departments, _ := w.GetSonDepartmentParentList(4)
	//for k, v := range departments {
	//	log.Println(k, "id=", v.Id, v)
	//}

	//log.Println("c==================")

	//w.CreateTag(work.Tag{
	//	TagName: "报警",
	//	TagId:   1,
	//})
	//w.CreateTag(work.Tag{
	//	TagName: "dev-deploy",
	//	TagId:   2,
	//})

	//userId := []string{}
	for k, u := range w.GetDepartmentUsers(4, 1) {
		log.Println("GetTagUser", k, u.Userid, u)
	}
	//
	////[{报警 1} {dev-deploy 2}]
	////log.Println(w.AddTagUsers([]string{"DengHaiZhuSheZhangGeGe"}, 2))
	//log.Println(w.AddTagUsers(userId, 2))
	//
	//for k, u := range w.GetTagList() {
	//	log.Println("GetTagList", k, u.TagId, u)
	//}
	//
	//for k, u := range w.GetTagUser(2) {
	//	log.Println("GetTagUser", k, u.Userid, u)
	//}

	//notify.SendText("DengHaiZhuSheZhangGeGe", "", "", "msg")
	//notify.SendText("", "", "2", "内网部署情况以后就用这个了,如果感觉到打扰可以把该通知设置成消息免打扰")
```
感谢支持
