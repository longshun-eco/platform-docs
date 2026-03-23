---
title: "enableAPIResponseCache"
source: "https://open.dingtalk.com/document/development/jsapi-enable-a-p-i-response-cache"
category: "客户端JSAPI / 基础API / 设备 / 内存不足处理"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-enable-a-p-i-response-cache_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-enable-a-p-i-response-cache_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

жӣҙж–°дәҺ 2025-10-16

ејҖеҗҜJSAPIиҝ”еӣһеҖјзј“еӯҳ

ејҖеҗҜ JSAPI иҝ”еӣһеҖјзј“еӯҳпјҢеңЁи°ғз”ЁиҖ—еҶ…еӯҳзҡ„ JSAPI еүҚи°ғз”ЁгҖӮ
ејҖеҗҜеҗҺпјҢдҪҝз”Ё getCachedAPIResponse иҺ·еҸ–и°ғз”ЁеҗҺзј“еӯҳзҡ„ JSAPI иҝ”еӣһеҖјгҖӮ

## ж”ҜжҢҒиҜҙжҳҺ

| еә”з”ЁиғҪеҠӣ | Android | iOS | Harmony | Mac | Windows | йў„и§Ҳж•Ҳжһң |
| --- | --- | --- | --- | --- | --- | --- |
| зҪ‘йЎөеә”з”ЁпјҲеҺҹH5еҫ®еә”з”Ёпјү | дёҚж”ҜжҢҒ | 8.0.15 | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | [еҺ»йў„и§Ҳ](https://open.dingtalk.com/tools/explorer/jsapi?id=11928) |
| е°ҸзЁӢеәҸ | дёҚж”ҜжҢҒ | 8.0.15 | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | [еҺ»йў„и§Ҳ](https://open.dingtalk.com/tools/explorer/jsapi?id=11928) |

## ж”ҜжҢҒеә”з”Ёзұ»еһӢ

| еә”з”Ёзұ»еһӢ | жҳҜеҗҰж”ҜжҢҒи°ғз”Ё |
| --- | --- |
| дјҒдёҡеҶ…йғЁеә”з”Ё | жҳҜ |
| з¬¬дёүж–№дјҒдёҡеә”з”Ё | жҳҜ |
| з¬¬дёүж–№дёӘдәәеә”з”Ё | жҳҜ |

## йүҙжқғи§„еҲҷ

еңЁH5еә”з”ЁдёӯпјҢи°ғз”Ё[dd.config](https://open.dingtalk.com/document/orgapp/jsapi-authentication)е®ҢжҲҗйүҙжқғеҗҺдҪҝз”Ё

еңЁе°ҸзЁӢеәҸеә”з”ЁдёӯпјҢж— йңҖйүҙжқғеҚіеҸҜзӣҙжҺҘи°ғз”Ё

## **еҸӮж•°иҜҙжҳҺ**

з»§жүҝ[йҖҡз”Ёиҫ“е…ҘеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§жҸҸиҝ°пјҡ

| еҗҚз§° | зұ»еһӢ | жҳҜеҗҰеҝ…еЎ« | зӨәдҫӢеҖј | жҸҸиҝ° |
| --- | --- | --- | --- | --- |
| enable | Boolean | жҳҜ | true | true ејҖеҗҜпјҢfalse е…ій—ӯ |

## **иҝ”еӣһз»“жһң**

з»§жүҝ[йҖҡз”Ёиҫ“еҮәеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§дёәз©ә

## **зӨәдҫӢ****д»Јз Ғ**

### й»ҳи®ӨDemoж Үйўҳ

```
dd.enableAPIResponseCache({
  enable: true,
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```