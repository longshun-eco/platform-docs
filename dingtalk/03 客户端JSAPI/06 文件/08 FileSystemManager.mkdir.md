---
title: "FileSystemManager.mkdir"
source: "https://open.dingtalk.com/document/development/jsapi-file-system-manager-mkdir"
category: "客户端JSAPI / 文件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-file-system-manager-mkdir_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-file-system-manager-mkdir_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

жӣҙж–°дәҺ 2025-08-27

и°ғз”ЁFileSystemManager.mkdirпјҢеҲӣе»әжң¬ең°з”ЁжҲ·зӣ®еҪ•гҖӮ

## ж”ҜжҢҒиҜҙжҳҺ

| еә”з”ЁиғҪеҠӣ | Android | iOS | Mac | Windows | йў„и§Ҳж•Ҳжһң |
| --- | --- | --- | --- | --- | --- |
| зҪ‘йЎөеә”з”ЁпјҲеҺҹH5еҫ®еә”з”Ёпјү | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | - |
| е°ҸзЁӢеәҸ | 6.5.26 | 6.5.26 | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | [еҺ»йў„и§Ҳ](https://open.dingtalk.com/tools/explorer/jsapi?id=10270) |

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
| dirPath | String | жҳҜ | ${dd.env.USER\_DATA\_PATH}/newDir | еҲӣе»әзҡ„зӣ®еҪ•и·Ҝеҫ„гҖӮ |
| recursive | Boolean | еҗҰ | /a/b/c | дҫӢеҰӮпјҢdirPathеҖјдёәпјҡ/a/b/cгҖӮ еҰӮжһңrecursiveдј trueпјҢеҲӣе»әзӣ®еҪ•ж—¶дјҡе…ҲеҲӣе»әaпјҢеҶҚеҲӣе»әbпјҢжңҖеҗҺеҶҚеҲӣе»әcгҖӮ еҰӮжһңrecursiveдј falseпјҢaгҖҒbгҖҒcеҸӘиҰҒжңүдёҖдёӘзӣ®еҪ•дёҚеӯҳеңЁпјҢжҺҘеҸЈдјҡжҸҗзӨәзҲ¶зә§зӣ®еҪ•дёҚеӯҳеңЁгҖӮ |

## **иҝ”еӣһз»“жһң**

з»§жүҝ[йҖҡз”Ёиҫ“еҮәеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§жҸҸиҝ°пјҡ

| еҗҚз§° | зұ»еһӢ | зӨәдҫӢеҖј | жҸҸиҝ° |
| --- | --- | --- | --- |
| success | Boolean | true | зӣ®еҪ•еҲӣе»әжҲҗеҠҹж—¶пјҢиҝ”еӣһtrueгҖӮ |

## **зӨәдҫӢ****д»Јз Ғ**

### й»ҳи®ӨеҮәе…ҘеҸӮ

```javascript
const fileSystemManager = dd.FileSystemManager();

fileSystemManager.mkdir({
  dirPath: '${dd.env.USER_DATA_PATH}/newDir',
  recursive: /a/b / c,
  success: (res) => {
    // res: true
  },
  fail: () => {},
  complete: () => {},
});
```

`success`иҝ”еӣһеҜ№иұЎзӨәдҫӢпјҡ

```
true
```