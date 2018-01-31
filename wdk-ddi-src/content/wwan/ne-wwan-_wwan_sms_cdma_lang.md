---
UID: NE:wwan._WWAN_SMS_CDMA_LANG
title: "_WWAN_SMS_CDMA_LANG"
author: windows-driver-content
description: The WWAN_SMS_CDMA_LANG enumeration lists the different SMS CDMA languages that are supported by the MB device.
old-location: netvista\wwan_sms_cdma_lang.htm
old-project: netvista
ms.assetid: 5294ce07-a4eb-4c21-88f1-04889dfbc1a1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/PWWAN_SMS_CDMA_LANG, wwan/WwanSmsCdmaLangJapanese, WwanSmsCdmaLangSpanish, wwan/WwanSmsCdmaLangKorean, wwan/WwanSmsCdmaLangHebrew, WwanSmsCdmaLangKorean, *PWWAN_SMS_CDMA_LANG, wwan/WwanSmsCdmaLangChinese, wwan/WwanSmsCdmaLangMax, WwanSmsCdmaLangJapanese, PWWAN_SMS_CDMA_LANG, wwan/WwanSmsCdmaLangEnglish, WwanSmsCdmaLangUnknown, WwanSmsCdmaLangFrench, WwanRef_21c9fcf4-07b0-43b3-86df-a2de613f5018.xml, netvista.wwan_sms_cdma_lang, PWWAN_SMS_CDMA_LANG enumeration pointer [Network Drivers Starting with Windows Vista], wwan/WwanSmsCdmaLangSpanish, WwanSmsCdmaLangHebrew, WWAN_SMS_CDMA_LANG, _WWAN_SMS_CDMA_LANG, wwan/WWAN_SMS_CDMA_LANG, WwanSmsCdmaLangMax, wwan/WwanSmsCdmaLangUnknown, WwanSmsCdmaLangChinese, wwan/WwanSmsCdmaLangFrench, WwanSmsCdmaLangEnglish, WWAN_SMS_CDMA_LANG enumeration [Network Drivers Starting with Windows Vista]
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




#### - WwanSmsCdmaLangUnknown

The message language is unknown.


#### - WwanSmsCdmaLangEnglish

The message is in English.


#### - WwanSmsCdmaLangFrench

The message is in French.


#### - WwanSmsCdmaLangSpanish

The message is in Spanish.


#### - WwanSmsCdmaLangJapanese

The message is in Japanese.


#### - WwanSmsCdmaLangKorean

The message is in Korean.


#### - WwanSmsCdmaLangChinese

The message is in Chinese.


#### - WwanSmsCdmaLangHebrew

The message is in Hebrew.


#### - WwanSmsCdmaLangMax

The total number of supported SMS CDMA languages.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_sms_cdma_record.md">WWAN_SMS_CDMA_RECORD</a>

<a href="..\wwan\ns-wwan-_wwan_sms_send_cdma.md">WWAN_SMS_SEND_CDMA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_CDMA_LANG enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

