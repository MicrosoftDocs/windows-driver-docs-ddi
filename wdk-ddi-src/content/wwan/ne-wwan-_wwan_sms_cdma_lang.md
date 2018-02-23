---
UID: NE:wwan._WWAN_SMS_CDMA_LANG
title: "_WWAN_SMS_CDMA_LANG"
author: windows-driver-content
description: The WWAN_SMS_CDMA_LANG enumeration lists the different SMS CDMA languages that are supported by the MB device.
old-location: netvista\wwan_sms_cdma_lang.htm
old-project: netvista
ms.assetid: 5294ce07-a4eb-4c21-88f1-04889dfbc1a1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WWAN_SMS_CDMA_LANG, wwan/WWAN_SMS_CDMA_LANG, wwan/WwanSmsCdmaLangKorean, WwanRef_21c9fcf4-07b0-43b3-86df-a2de613f5018.xml, WwanSmsCdmaLangUnknown, WwanSmsCdmaLangJapanese, wwan/WwanSmsCdmaLangHebrew, PWWAN_SMS_CDMA_LANG, WwanSmsCdmaLangSpanish, _WWAN_SMS_CDMA_LANG, WwanSmsCdmaLangChinese, wwan/WwanSmsCdmaLangEnglish, PWWAN_SMS_CDMA_LANG enumeration pointer [Network Drivers Starting with Windows Vista], wwan/WwanSmsCdmaLangJapanese, WWAN_SMS_CDMA_LANG enumeration [Network Drivers Starting with Windows Vista], WwanSmsCdmaLangHebrew, wwan/WwanSmsCdmaLangUnknown, WwanSmsCdmaLangEnglish, WwanSmsCdmaLangKorean, wwan/WwanSmsCdmaLangSpanish, netvista.wwan_sms_cdma_lang, *PWWAN_SMS_CDMA_LANG, wwan/PWWAN_SMS_CDMA_LANG, WwanSmsCdmaLangFrench, wwan/WwanSmsCdmaLangMax, wwan/WwanSmsCdmaLangChinese, wwan/WwanSmsCdmaLangFrench, WwanSmsCdmaLangMax
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_SMS_CDMA_LANG
product: Windows
targetos: Windows
req.typenames: WWAN_SMS_CDMA_LANG, *PWWAN_SMS_CDMA_LANG
req.product: Windows 10 or later.
---

# _WWAN_SMS_CDMA_LANG enumeration


## -description


The WWAN_SMS_CDMA_LANG enumeration lists the different SMS CDMA languages that are supported by the
  MB device.


## -syntax


````
typedef enum _WWAN_SMS_CDMA_LANG { 
  WwanSmsCdmaLangUnknown   = 0,
  WwanSmsCdmaLangEnglish,
  WwanSmsCdmaLangFrench,
  WwanSmsCdmaLangSpanish,
  WwanSmsCdmaLangJapanese,
  WwanSmsCdmaLangKorean,
  WwanSmsCdmaLangChinese,
  WwanSmsCdmaLangHebrew,
  WwanSmsCdmaLangMax
} WWAN_SMS_CDMA_LANG, *PWWAN_SMS_CDMA_LANG;
````


## -enum-fields




### -field WwanSmsCdmaLangUnknown

The message language is unknown.


### -field WwanSmsCdmaLangEnglish

The message is in English.


### -field WwanSmsCdmaLangFrench

The message is in French.


### -field WwanSmsCdmaLangSpanish

The message is in Spanish.


### -field WwanSmsCdmaLangJapanese

The message is in Japanese.


### -field WwanSmsCdmaLangKorean

The message is in Korean.


### -field WwanSmsCdmaLangChinese

The message is in Chinese.


### -field WwanSmsCdmaLangHebrew

The message is in Hebrew.


### -field WwanSmsCdmaLangMax

The total number of supported SMS CDMA languages.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_sms_send_cdma.md">WWAN_SMS_SEND_CDMA</a>



<a href="..\wwan\ns-wwan-_wwan_sms_cdma_record.md">WWAN_SMS_CDMA_RECORD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_CDMA_LANG enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

