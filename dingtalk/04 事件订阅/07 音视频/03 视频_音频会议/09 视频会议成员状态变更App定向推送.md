---
title: "视频会议成员状态变更App定向推送"
source: "https://open.dingtalk.com/document/development/events-meeting-member-status-change-target-push"
category: "事件订阅 / 音视频 / 视频/音频会议"
updated: 
tags:
  - dingtalk
  - 事件订阅
---
![[development-events-meeting-member-status-change-target-push_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-events-meeting-member-status-change-target-push_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

жӣҙж–°дәҺ 2025-08-27

## дәӢд»¶дҝЎжҒҜ

| еҗҚз§° | еҖј |
| --- | --- |
| дёӯж–ҮеҗҚз§° | и§Ҷйў‘дјҡи®®жҲҗе‘ҳзҠ¶жҖҒеҸҳжӣҙAppе®ҡеҗ‘жҺЁйҖҒ |
| иӢұж–ҮеҗҚз§° | meeting\_member\_status\_change\_target\_push |

## еҠҹиғҪжҸҸиҝ°

и§Ҷйў‘дјҡи®®жҲҗе‘ҳзҠ¶жҖҒеҸҳжӣҙе®ҡеҗ‘жҺЁйҖҒпјҢзӣ®еүҚж”ҜжҢҒе®ҡеҗ‘жҺЁйҖҒйҖҡиҝҮејҖж”ҫжҺҘеҸЈеҲӣе»әзҡ„дјҡи®®жҲҗе‘ҳдәӢд»¶пјҢе®ҡеҗ‘жҺЁйҖҒз»ҷи°ғз”Ёж–№жүҖеұһзҡ„еә”з”ЁгҖӮ

## ж”ҜжҢҒеә”з”Ёзұ»еһӢ

| еә”з”Ёзұ»еһӢ | StreamжЁЎејҸжҺЁйҖҒ | HTTPжҺЁйҖҒ | SyncHTTP/RDSжҺЁйҖҒ |
| --- | --- | --- | --- |
| дјҒдёҡеҶ…йғЁеә”з”Ё | ж”ҜжҢҒ | ж”ҜжҢҒ | дёҚж”ҜжҢҒ |
| з¬¬дёүж–№дјҒдёҡеә”з”Ё | ж”ҜжҢҒ | дёҚж”ҜжҢҒ | ж”ҜжҢҒ |

## дәӢд»¶дҪ“жҸҸиҝ°

StreamжЁЎејҸжҺЁйҖҒ

| еҗҚз§° | зұ»еһӢ | зӨәдҫӢеҖј | жҸҸиҝ° |
| --- | --- | --- | --- |
| eventUnifiedAppId | String | bbb381b6-f01xxxxx58daac | з»ҹдёҖеә”з”Ёиә«д»ҪIdгҖӮ |
| eventCorpId | String | ding9f50b15bxxxx16741 | дәӢд»¶жүҖеұһзҡ„corpIdгҖӮ |
| eventType | String | meeting\_member\_status\_change\_target\_push | дәӢд»¶зұ»еһӢгҖӮ |
| eventId | String | c7c7120f2c07419\*\*ebdba0318c8 | дәӢд»¶зҡ„е”ҜдёҖIdгҖӮ |
| eventBornTime | Long | 1683533823336 | дәӢд»¶з”ҹжҲҗж—¶й—ҙгҖӮ |
| data | Object |  | дәӢд»¶дҪ“dataгҖӮ |

### **дәӢд»¶дҪ“зӨәдҫӢ**

```
{
```

HTTPжҺЁйҖҒ

| еҗҚз§° | зұ»еһӢ | зӨәдҫӢеҖј | жҸҸиҝ° |
| --- | --- | --- | --- |
| EventType | String | meeting\_member\_status\_change\_target\_push | дәӢд»¶иӢұж–ҮеҗҚз§°гҖӮ |
| EventTime | Long | 1663143335567 | дәӢд»¶еҸ‘з”ҹзҡ„ж—¶й—ҙгҖӮ |
| CorpId | String | ding9f50b15bxxxx16741 | дјҒдёҡcorpIdгҖӮ |
| BizId | String | 1663\*\*35567 | ж— дёҡеҠЎж„Ҹд№үпјҢе№ӮзӯүгҖӮ |
| eventId | String | c7c7120f2c07419\*\*ebdba0318c8 | дәӢд»¶зҡ„е”ҜдёҖIdгҖӮ |
| openMemberModels | Array<Object> |  | еҸҳжӣҙзҡ„жҲҗе‘ҳдҝЎжҒҜеҲ—иЎЁгҖӮ |
| statusSeqNum | Integer | 2 | дјҡи®®гҖҒжҲҗе‘ҳдҝЎжҒҜжҖ»дҪ“еәҸеҲ—еҸ·, з”ЁдәҺеҢәеҲҶж¶ҲжҒҜйЎәеәҸгҖӮ |
| changeScene | String | user\_join | жҲҗе‘ҳзҠ¶жҖҒеҸҳеҢ–з»ҶеҲҶзұ»еһӢпјҡ   * user\_joinпјҡжҲҗе‘ҳе…ҘдјҡдәӢд»¶ * user\_leaveпјҡжҲҗе‘ҳзҰ»дјҡдәӢд»¶ * user\_invitedпјҡжҲҗе‘ҳиў«йӮҖиҜ·дәӢд»¶ * user\_kickedпјҡжҲҗе‘ҳиў«иёўдәӢд»¶ |

### **дәӢд»¶дҪ“зӨәдҫӢ**

```
{
```

SyncHTTP/RDSжҺЁйҖҒ

дёәRDSжҺЁйҖҒж–№ејҸж—¶пјҢж•°жҚ®жҸ’е…ҘиЎЁopen\_sync\_biz\_data\_mediumдёӯгҖӮ

| еҗҚз§° | зұ»еһӢ | зӨәдҫӢеҖј | жҸҸиҝ° |
| --- | --- | --- | --- |
| corp\_id | String | ding9f50b15bxxxx16741 | дјҒдёҡcorp\_idгҖӮ |
| biz\_id | String | 1663\*\*35567 | biz\_idж— дёҡеҠЎж„Ҹд№үпјҢе№ӮзӯүгҖӮ |
| biz\_type | Integer | 349 | дәӢд»¶bizTypeгҖӮ |
| biz\_data | Object |  | дәӢд»¶bizDataд»Ӣз»ҚгҖӮ |

### **biz\_dataж•°жҚ®зӨәдҫӢ(biz\_type=349)**

```json
{
  "corp_id": "ding9f50b15bxxxx16741",
  "biz_id": "1663**35567",
  "biz_type": 349,
  "biz_data": {
    "eventId": "c7c7120f2c07419**ebdba0318c8",
    "syncAction": "meeting_member_status_change_target_push",
    "openMemberModels": [
      {
        "duration": 1000,
        "leaveTime": 1663143344000,
        "deviceType": "Android",
        "pstnJoin": false,
        "joinTime": 1663143334000,
        "userNick": "дјҡи®®еҸӮдјҡиҖ…",
        "conferenceId": "6321*******9b6ed40",
        "attendStatus": 3,
        "host": false,
        "coHost": true,
        "userId": "2iPO*********wiEiE"
      }
```