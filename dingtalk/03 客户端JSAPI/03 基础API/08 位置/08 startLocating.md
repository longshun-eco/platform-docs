---
title: "startLocating"
source: "https://open.dingtalk.com/document/development/jsapi-start-locating"
category: "客户端JSAPI / 基础API / 位置"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-start-locating_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-start-locating_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

жӣҙж–°дәҺ 2025-08-27

и°ғз”ЁstartLocatingпјҢиҝһз»ӯиҺ·еҸ–еҪ“еүҚең°зҗҶдҪҚзҪ®дҝЎжҒҜпјҲжҢҒз»ӯе®ҡдҪҚпјүгҖӮ

з”ЁдәҺеҜ№е®ҡдҪҚзІҫеәҰиҰҒжұӮиҫғй«ҳд»ҘеҸҠйңҖиҰҒжҢҒз»ӯжӣҙж–°з”ЁжҲ·дҪҚзҪ®зҡ„еңәжҷҜпјҢйҖҡиҝҮжҢҒз»ӯжҺҘж”¶callbackж–№ејҸпјҢиҺ·еҸ–з”ЁжҲ·еҪ“еүҚзҡ„дҪҚзҪ®дҝЎжҒҜгҖӮиҝһз»ӯе®ҡдҪҚеҠҹиғҪпјҢз”ұдёүдёӘжҺҘеҸЈз»„жҲҗпјҢејҖе§Ӣиҝһз»ӯе®ҡдҪҚ(startLocating)гҖҒеҒңжӯўиҝһз»ӯе®ҡдҪҚ(stopLocating)гҖҒд»ҘеҸҠиҺ·еҸ–еҪ“еүҚе®ҡдҪҚзҠ¶жҖҒ(getLocatingStatus)гҖӮ

## ж”ҜжҢҒиҜҙжҳҺ

| еә”з”ЁиғҪеҠӣ | Android | iOS | Harmony | Mac | Windows | йў„и§Ҳж•Ҳжһң |
| --- | --- | --- | --- | --- | --- | --- |
| зҪ‘йЎөеә”з”ЁпјҲеҺҹH5еҫ®еә”з”Ёпјү | 6.0.0 | 6.0.0 | 7.0.0 | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | [еҺ»йў„и§Ҳ](https://open.dingtalk.com/tools/explorer/jsapi?id=11678) |
| е°ҸзЁӢеәҸ | 6.0.0 | 6.0.0 | 7.0.0 | дёҚж”ҜжҢҒ | дёҚж”ҜжҢҒ | [еҺ»йў„и§Ҳ](https://open.dingtalk.com/tools/explorer/jsapi?id=11678) |

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
| targetAccuracy | Number | жҳҜ | 200 | жңҹжңӣе®ҡдҪҚзІҫеәҰеҚҠеҫ„(еҚ•дҪҚзұі)е®ҡдҪҚз»“жһңе°ҪйҮҸж»Ўи¶іиҜҘеҸӮж•°иҰҒжұӮпјҢдёҚдҝқиҜҒе°ҸдәҺиҜҘиҜҜе·®пјҢејҖеҸ‘иҖ…йңҖиҰҒиҜ»еҸ–иҝ”еӣһз»“жһңзҡ„ accuracy еӯ—ж®өж ЎйӘҢеқҗж ҮзІҫеәҰгҖӮ  е»әи®®жҢүз…§дёҡеҠЎйңҖжұӮи®ҫзҪ®е®ҡдҪҚзІҫеәҰпјҢжҺЁиҚҗйҮҮз”Ё200mпјҢеҸҜиҺ·еҫ—иҫғеҘҪзҡ„зІҫеәҰе’Ңиҫғзҹӯзҡ„е“Қеә”ж—¶й•ҝгҖӮ |
| iOSDistanceFilter | Number | жҳҜ | 10 | iOSз«ҜдҪҚзҪ®еҸҳжӣҙж•Ҹж„ҹеәҰпјҢеҚ•дҪҚдёәmпјҢжӯӨеҖјдјҡеҪұе“ҚiOSз«Ҝcallbackеӣһи°ғйҖҹзҺҮгҖӮ  iOSз«ҜеҸӮж•°гҖӮ |
| useCache | Boolean | жҳҜ | true | жҳҜеҗҰдҪҝз”Ёзј“еӯҳпјҡ   * trueпјҡй»ҳи®ӨеҖјпјҢи®ҫзҪ®trueпјҢе®ўжҲ·з«Ҝзј“еӯҳе®ҡдҪҚзҡ„ең°зҗҶдҪҚзҪ®дҝЎжҒҜпјҢеңЁзј“еӯҳжңҹеҶ…(еҲҶй’ҹ)еҶҚж¬Ўе®ҡдҪҚдјҡиҝ”еӣһж—§зҡ„е®ҡдҪҚгҖӮ * falseпјҡи®ҫзҪ®falseпјҢдёҚзј“еӯҳең°еқҖдҪҚзҪ®дҝЎжҒҜгҖӮ   Androidз«ҜеҸӮж•°гҖӮ |
| withReGeocode | Boolean | жҳҜ | false | жҳҜеҗҰйңҖиҰҒеёҰжңүйҖҶең°зҗҶзј–з ҒдҝЎжҒҜгҖӮ  * й»ҳи®ӨдёәfalseгҖӮ * иҜҘеҠҹиғҪйңҖиҰҒзҪ‘з»ңиҜ·жұӮпјҢиҜ·ж №жҚ®иҮӘе·ұзҡ„дёҡеҠЎеңәжҷҜдҪҝз”ЁгҖӮ |
| callBackInterval | Number | жҳҜ | 1000 | еӣһдј ж—¶й—ҙй—ҙйҡ”пјҢеҚ•дҪҚmsгҖӮ |
| sceneId | String | жҳҜ | \*\*\*\* | е®ҡдҪҚеңәжҷҜidгҖӮ  еҜ№дәҺеҗҢдёҖidпјҢдёҚеҸҜиҝһз»ӯstartпјҢеҗҰеҲҷдјҡжҠҘй”ҷгҖӮдёҚеҗҢscenceIdдә’дёҚеҪұе“ҚгҖӮ |

## **иҝ”еӣһз»“жһң**

з»§жүҝ[йҖҡз”Ёиҫ“еҮәеҜ№иұЎ](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)пјҢжү©еұ•еұһжҖ§жҸҸиҝ°пјҡ

| еҗҚз§° | зұ»еһӢ | зӨәдҫӢеҖј | жҸҸиҝ° |
| --- | --- | --- | --- |
| longitude | Number | 117.451692 | з»ҸеәҰгҖӮ |
| latitude | Number | 119.451692 | зә¬еәҰгҖӮ |
| accuracy | Number | 200 | е®һйҷ…зҡ„е®ҡдҪҚзІҫеәҰеҚҠеҫ„ (еҚ•дҪҚзұі)гҖӮ |
| address | String | еҢ—дә¬еёӮжңқйҳіеҢәеҚ—зЈЁжҲҝй•ҮеҢ—дә¬еӣҪе®¶е№ҝе‘Ҡдә§дёҡеӣӯеҢә | ж јејҸеҢ–ең°еқҖгҖӮ  еҰӮйңҖиҝ”еӣһиҜҘеҸӮж•°пјҢиҜ·дҪҝз”Ёй«ҳеҫ·еқҗж Үе№¶е°Ҷ**withReGeocode**еҸӮж•°и®ҫзҪ®дёә**true**гҖӮ |
| province | String | еҢ—дә¬еёӮ | зңҒд»ҪгҖӮ  еҰӮйңҖиҝ”еӣһиҜҘеҸӮж•°пјҢиҜ·дҪҝз”Ёй«ҳеҫ·еқҗж Үе№¶е°Ҷ**withReGeocode**еҸӮж•°и®ҫзҪ®дёә**true**гҖӮ |
| city | String | еҢ—дә¬еёӮ | еҹҺеёӮгҖӮ  зӣҙиҫ–еёӮдјҡиҝ”еӣһз©әгҖӮ |
| district | String | жңқйҳіеҢә | иЎҢж”ҝеҢәгҖӮ |
| road | String | иҘҝеӨ§жңӣи·Ҝз”І12-2еҸ·жҘјгҖӮ | иЎ—йҒ“гҖӮ |
| netType | String | wifi | еҪ“еүҚи®ҫеӨҮзҪ‘з»ңзұ»еһӢгҖӮ |
| operatorType | String | CMCC | еҪ“еүҚи®ҫеӨҮдҪҝз”Ёз§»еҠЁиҝҗиҗҘе•ҶгҖӮ |
| locationType | Number | 1 | дҪҚзҪ®зұ»еһӢпјҡ   * 1пјҡGPSе®ҡдҪҚз»“жһң * 2пјҡиҝ”еӣһдёҠж¬Ўе®ҡдҪҚз»“жһң * 3пјҡзј“еӯҳе®ҡдҪҚз»“жһң * 4пјҡWifiе®ҡдҪҚз»“жһң * 5пјҡеҹәз«ҷе®ҡдҪҚз»“жһң |
| errorMessage | String | иҝ”еӣһз ҒжҸҸиҝ° | иҝ”еӣһз ҒжҸҸиҝ°гҖӮ |
| errorCode | Number | иҝ”еӣһз Ғ | иҝ”еӣһз ҒгҖӮ |
| isWifiEnabled | Boolean | true | wifiи®ҫзҪ®жҳҜеҗҰејҖеҗҜпјҢдёҚдҝқиҜҒе·ІиҝһжҺҘдёҠгҖӮ  д»…Androidж”ҜжҢҒгҖӮ |
| isGpsEnabled | Boolean | true | gpsи®ҫзҪ®жҳҜеҗҰејҖеҗҜпјҢдёҚдҝқиҜҒе·ІиҝһжҺҘдёҠгҖӮ  д»…Androidж”ҜжҢҒгҖӮ |
| isFromMock | Boolean | true | е®ҡдҪҚиҝ”еӣһзҡ„з»Ҹзә¬еәҰжҳҜеҗҰжҳҜжЁЎжӢҹзҡ„з»“жһңгҖӮ  д»…Androidж”ҜжҢҒгҖӮ |
| provider | String | wifi | ж··еҗҲе®ҡдҪҚпјҢе…·дҪ“е®ҡдҪҚжҸҗдҫӣиҖ…жңүwifiгҖҒlbsгҖҒgpsиҝҷдёүз§ҚгҖӮ |
| isMobileEnabled | Boolean | true | з§»еҠЁзҪ‘з»ңжҳҜи®ҫзҪ®жҳҜеҗҰејҖеҗҜпјҢдёҚдҝқиҜҒе·ІиҝһжҺҘдёҠгҖӮ  д»…Androidж”ҜжҢҒгҖӮ |

## **зӨәдҫӢ****д»Јз Ғ**

### й»ҳи®ӨеҮәе…ҘеҸӮ

```javascript
dd.startLocating({
  sceneId: '****',
  useCache: true,
  withReGeocode: fal,
  targetAccuracy: 200,
  callBackInterval: 1000,
  iOSDistanceFilter: Number,
  success: (res) => {
    const {
      city,
      road,
      address,
      netType,
      accuracy,
      district,
      latitude,
      provider,
      province,
      errorCode,
      longitude,
      isFromMock,
```

`success`иҝ”еӣһеҜ№иұЎзӨәдҫӢпјҡ

```json
{"loc":{"start":{"line":1,"column":165},"end":{"line":1,"column":168}},"codeFrame":"> 1 | {city:'еҢ—дә¬еёӮ',road:'иҘҝеӨ§жңӣи·Ҝз”І12-2еҸ·жҘјгҖӮ',address:'еҰӮпјҡеҢ—дә¬еёӮжңқйҳіеҢәеҚ—зЈЁжҲҝй•ҮеҢ—дә¬еӣҪе®¶е№ҝе‘Ҡдә§дёҡеӣӯеҢәгҖӮ',netType:'wifi',accuracy:200,district:'жңқйҳіеҢә',latitude:119.,provider:'wifi',province:'еҢ—дә¬еёӮ',errorCode:иҝ”еӣһз Ғ,longitude:100,isFromMock:true,errorMessage:'иҝ”еӣһз ҒжҸҸиҝ°',isGpsEnabled:true,locationType:1,operatorType:'CMCC',isWifiEnabled:true,isMobileEnabled:true,}\n    |                                                                                                                                                                     ^^^"}
```