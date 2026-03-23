---
title: "startRecord"
source: "https://open.dingtalk.com/document/development/jsapi-start-record"
category: "客户端JSAPI / 基础API / 多媒体 / 录音"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-start-record_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-start-record_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

жӣҙж–°дәҺ 2025-08-27

и°ғз”ЁstartRecordпјҢејҖе§ӢеҪ•йҹігҖӮ

## ж”ҜжҢҒиҜҙжҳҺ

| еә”з”ЁиғҪеҠӣ | Android | iOS | Harmony | Mac | Windows | йў„и§Ҳж•Ҳжһң |
| --- | --- | --- | --- | --- | --- | --- |
| зҪ‘йЎөеә”з”ЁпјҲеҺҹH5еҫ®еә”з”Ёпјү | 6.0.0 | 6.0.0 | 7.0.0 | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | [еҺ»йў„и§Ҳ](https://open.dingtalk.com/tools/explorer/jsapi?id=11702) |
| е°ҸзЁӢеәҸ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | - |

## ж”ҜжҢҒеә”з”Ёзұ»еһӢ

| еә”з”Ёзұ»еһӢ | жҳҜеҗҰж”ҜжҢҒи°ғз”Ё |
| --- | --- |
| дјҒдёҡеҶ…йғЁеә”з”Ё | жҳҜ |
| з¬¬дёүж–№дјҒдёҡеә”з”Ё | жҳҜ |
| з¬¬дёүж–№дёӘдәәеә”з”Ё | жҳҜ |

## йүҙжқғи§„еҲҷ

и°ғз”Ё[dd.config](https://open.dingtalk.com/document/orgapp/jsapi-authentication)е®ҢжҲҗйүҙжқғеҗҺдҪҝз”Ё

## **еҸӮж•°иҜҙжҳҺ**

з»§жүҝ[йҖҡз”Ёиҫ“е…ҘеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§жҸҸиҝ°пјҡ

| еҗҚз§° | зұ»еһӢ | жҳҜеҗҰеҝ…еЎ« | зӨәдҫӢеҖј | жҸҸиҝ° |
| --- | --- | --- | --- | --- |
| maxDuration | Number | еҗҰ | 3 | еҸҜйҖүеҸӮж•°пјҢеҪ•йҹіжңҖеӨ§ж—¶й•ҝпјҢеҚ•дҪҚпјҡз§’пјҢеҝ…йЎ»дёәж•ҙж•°пјҢиҢғеӣҙ[1,300]гҖӮ |

## **иҝ”еӣһз»“жһң**

з»§жүҝ[йҖҡз”Ёиҫ“еҮәеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§дёәз©ә

## **зӨәдҫӢ****д»Јз Ғ**

### й»ҳи®ӨеҮәе…ҘеҸӮ

```
dd.startRecord({
  maxDuration: 3,
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```