---
title: "onPullDownRefresh"
source: "https://open.dingtalk.com/document/development/jsapi-on-pull-down-refresh"
category: "客户端JSAPI / 基础API / 界面 / 下拉刷新"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-on-pull-down-refresh_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-on-pull-down-refresh_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

жӣҙж–°дәҺ 2025-08-27

зӣ‘еҗ¬дёӢжӢүеҲ·ж–°

еңЁ Page дёӯиҮӘе®ҡд№ү onPullDownRefresh еҮҪж•°пјҢеҸҜд»Ҙзӣ‘еҗ¬иҜҘйЎөйқўз”ЁжҲ·зҡ„дёӢжӢүеҲ·ж–°дәӢд»¶пјҡ

йңҖиҰҒеңЁйЎөйқўеҜ№еә”зҡ„.jsonй…ҚзҪ®ж–Үд»¶дёӯй…ҚзҪ®"pullRefresh": trueйҖүйЎ№пјҢжүҚиғҪејҖеҗҜдёӢжӢүеҲ·ж–°дәӢд»¶

еҪ“еӨ„зҗҶе®Ңж•°жҚ®еҲ·ж–°еҗҺпјҢи°ғз”Ёdd.stopPullDownRefreshеҸҜд»ҘеҒңжӯўеҪ“еүҚйЎөйқўзҡ„дёӢжӢүеҲ·ж–°гҖӮ

## ж”ҜжҢҒиҜҙжҳҺ

| еә”з”ЁиғҪеҠӣ | Android | iOS | Harmony | Mac | Windows | йў„и§Ҳж•Ҳжһң |
| --- | --- | --- | --- | --- | --- | --- |
| зҪ‘йЎөеә”з”ЁпјҲеҺҹH5еҫ®еә”з”Ёпјү | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | - |
| е°ҸзЁӢеәҸ | 6.0.0 | 6.0.0 | 7.0.0 | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | [еҺ»йў„и§Ҳ](https://open.dingtalk.com/tools/explorer/jsapi?id=11578) |

## ж”ҜжҢҒеә”з”Ёзұ»еһӢ

| еә”з”Ёзұ»еһӢ | жҳҜеҗҰж”ҜжҢҒи°ғз”Ё |
| --- | --- |
| дјҒдёҡеҶ…йғЁеә”з”Ё | жҳҜ |
| з¬¬дёүж–№дјҒдёҡеә”з”Ё | жҳҜ |
| з¬¬дёүж–№дёӘдәәеә”з”Ё | жҳҜ |

## йүҙжқғи§„еҲҷ

ж— йңҖйүҙжқғеҚіеҸҜзӣҙжҺҘи°ғз”Ё

## **еҸӮж•°иҜҙжҳҺ**

з»§жүҝ[йҖҡз”Ёиҫ“е…ҘеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§дёәз©ә

## **иҝ”еӣһз»“жһң**

з»§жүҝ[йҖҡз”Ёиҫ“еҮәеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§дёәз©ә

## **зӨәдҫӢ****д»Јз Ғ**

### Page дёӯе®ҡд№ү onPullDownRefresh еӨ„зҗҶеҮҪж•°

```
Page({
  onPullDownRefresh() {
    console.log('onPullDownRefresh');
  },
});
```