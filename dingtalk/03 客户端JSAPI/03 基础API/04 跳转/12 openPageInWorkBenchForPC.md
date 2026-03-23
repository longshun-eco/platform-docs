---
title: "openPageInWorkBenchForPC"
source: "https://open.dingtalk.com/document/development/jsapi-open-page-in-work-bench-for-pc"
category: "客户端JSAPI / 基础API / 跳转"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-open-page-in-work-bench-for-pc_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-open-page-in-work-bench-for-pc_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

жӣҙж–°дәҺ 2025-08-27

и°ғз”ЁopenPageInWorkBenchForPCеңЁPCз«Ҝжү“ејҖж–°еј№зӘ—йЎөйқўгҖӮ

еңЁй’үй’үз”өи„‘е®ўжҲ·з«Ҝе·ҘдҪңеҸ°зҡ„еҫ®еә”з”ЁйЎөйқўеҶ…и°ғз”Ёжң¬жҺҘеҸЈпјҢи°ғз”Ёж•ҲжһңеҰӮдёӢеӣҫжүҖзӨәпјҢй’үй’үе®ўжҲ·з«Ҝдјҡеј№еҮәдёҖдёӘеј№зӘ—йЎөйқўпјҢеј№зӘ—йЎөйқўеҶ…жү“ејҖжҢҮе®ҡзҡ„йЎөйқўең°еқҖгҖӮ

![[development-jsapi-open-page-in-work-bench-for-pc_p425990.png]]

## ж”ҜжҢҒиҜҙжҳҺ

| еә”з”ЁиғҪеҠӣ | Android | iOS | Harmony | Mac | Windows | йў„и§Ҳж•Ҳжһң |
| --- | --- | --- | --- | --- | --- | --- |
| зҪ‘йЎөеә”з”ЁпјҲеҺҹH5еҫ®еә”з”Ёпјү | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | 6.0.8 | 6.0.8 | [еҺ»йў„и§Ҳ](https://open.dingtalk.com/tools/explorer/jsapi?id=11694) |
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
| app\_url | String | жҳҜ | https://www.dingtalk.com | еј№зӘ—йЎөйқўзҡ„й“ҫжҺҘең°еқҖгҖӮ |
| app\_info | Object | еҗҰ |  | еј№зӘ—йЎөйқўзҡ„й…ҚзҪ®дҝЎжҒҜгҖӮ |

## **иҝ”еӣһз»“жһң**

з»§жүҝ[йҖҡз”Ёиҫ“еҮәеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§жҸҸиҝ°пјҡ

| еҗҚз§° | зұ»еһӢ | зӨәдҫӢеҖј | жҸҸиҝ° |
| --- | --- | --- | --- |
| body | Boolean | true | и°ғз”ЁжҲҗеҠҹж—¶пјҢиҝ”еӣһз»“жһңдёә{"body":true}гҖӮ |

## **зӨәдҫӢ****д»Јз Ғ**

### й»ҳи®ӨеҮәе…ҘеҸӮ

```javascript
dd.openPageInWorkBenchForPC({
  app_url: 'https://www.dingtalk.com',
  app_info: {
    app_tab_key: '123',
    app_active_if_exist: true,
    app_refresh_if_exist: true,
  },
  success: (res) => {
    const { body } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`иҝ”еӣһеҜ№иұЎзӨәдҫӢпјҡ

```json
{ "body": true }
```