---
title: "getSystemSettings"
source: "https://open.dingtalk.com/document/development/jsapi-get-system-settings"
category: "客户端JSAPI / 基础API / 设备 / 系统信息"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-system-settings_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-system-settings_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

жӣҙж–°дәҺ 2025-08-27

и°ғз”ЁgetSystemSettingsпјҢжү“ејҖзі»з»ҹи®ҫзҪ®гҖӮ

## ж”ҜжҢҒиҜҙжҳҺ

| еә”з”ЁиғҪеҠӣ | Android | iOS | Harmony | Mac | Windows | йў„и§Ҳж•Ҳжһң |
| --- | --- | --- | --- | --- | --- | --- |
| зҪ‘йЎөеә”з”ЁпјҲеҺҹH5еҫ®еә”з”Ёпјү | 4.6.36 | 6.3.15 | 7.0.0 | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | [еҺ»йў„и§Ҳ](https://open.dingtalk.com/tools/explorer/jsapi?id=11671) |
| е°ҸзЁӢеәҸ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | - |

## ж”ҜжҢҒеә”з”Ёзұ»еһӢ

| еә”з”Ёзұ»еһӢ | жҳҜеҗҰж”ҜжҢҒи°ғз”Ё |
| --- | --- |
| дјҒдёҡеҶ…йғЁеә”з”Ё | жҳҜ |
| з¬¬дёүж–№дјҒдёҡеә”з”Ё | жҳҜ |
| з¬¬дёүж–№дёӘдәәеә”з”Ё | жҳҜ |

## йүҙжқғи§„еҲҷ

ж— йңҖйүҙжқғеҚіеҸҜзӣҙжҺҘи°ғз”Ё

## **еҸӮж•°иҜҙжҳҺ**

з»§жүҝ[йҖҡз”Ёиҫ“е…ҘеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§жҸҸиҝ°пјҡ

| еҗҚз§° | зұ»еһӢ | жҳҜеҗҰеҝ…еЎ« | зӨәдҫӢеҖј | жҸҸиҝ° |
| --- | --- | --- | --- | --- |
| action | String | еҗҰ | android.settings.BLUETOOTH\_SETTINGS | Androidзі»з»ҹдёӯactionзҡ„жҰӮеҝөгҖӮ дҫӢеҰӮпјҡ**android.settings.BLUETOOTH\_SETTINGS**пјҡжү“ејҖи“қзүҷи®ҫзҪ®йЎөйқў жӣҙеӨҡactionеҸӮиҖғ[иҜҰжғ…](https://developer.android.com/reference/android/provider/Settings?spm=ding_open_doc.document.0.0.51e94a97hKpRAM)гҖӮ  д»…Androidзі»з»ҹйңҖиҰҒеЎ«еҶҷгҖӮ |
| param | String | еҗҰ | extended data | Androidзі»з»ҹдёӯи·іиҪ¬зі»з»ҹеә”з”ЁжүҖйңҖзҡ„extraеҸӮж•°гҖӮ  д»…Androidзі»з»ҹйңҖиҰҒеЎ«еҶҷгҖӮ |
| data | String | еҗҰ | data param | Androidзі»з»ҹдёӯи·іиҪ¬зі»з»ҹеә”з”ЁжүҖйңҖзҡ„dataеҸӮж•°гҖӮ  д»…Androidзі»з»ҹйңҖиҰҒеЎ«еҶҷгҖӮ |

## **иҝ”еӣһз»“жһң**

з»§жүҝ[йҖҡз”Ёиҫ“еҮәеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§дёәз©ә

## **зӨәдҫӢ****д»Јз Ғ**

### й»ҳи®ӨеҮәе…ҘеҸӮ

```
dd.getSystemSettings({
  data: 'data param',
  param: '"extended data',
  action: 'android.settings.BLUETOOTH_SETTINGS',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```