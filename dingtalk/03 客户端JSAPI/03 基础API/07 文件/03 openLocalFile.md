---
title: "openLocalFile"
source: "https://open.dingtalk.com/document/development/jsapi-open-local-file"
category: "客户端JSAPI / 基础API / 文件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-open-local-file_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-open-local-file_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

жӣҙж–°дәҺ 2025-08-27

и°ғз”ЁopenLocalFileпјҢжү“ејҖжң¬ең°ж–Үд»¶гҖӮ

## ж”ҜжҢҒиҜҙжҳҺ

| еә”з”ЁиғҪеҠӣ | Android | iOS | Mac | Windows | йў„и§Ҳж•Ҳжһң |
| --- | --- | --- | --- | --- | --- |
| зҪ‘йЎөеә”з”ЁпјҲеҺҹH5еҫ®еә”з”Ёпјү | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | 6.0.0 | 6.0.0 | [еҺ»йў„и§Ҳ](https://open.dingtalk.com/tools/explorer/jsapi?id=11663) |
| е°ҸзЁӢеәҸ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | - |

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
| url | String | жҳҜ |  | urlжҳҜзј“еӯҳж–Үд»¶зҡ„keyгҖӮ |

## **иҝ”еӣһз»“жһң**

з»§жүҝ[йҖҡз”Ёиҫ“еҮәеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§дёәз©ә

## **зӨәдҫӢ****д»Јз Ғ**

### й»ҳи®ӨеҮәе…ҘеҸӮ

```
dd.openLocalFile({
  url: `urlзӨәдҫӢеҖј`,
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```