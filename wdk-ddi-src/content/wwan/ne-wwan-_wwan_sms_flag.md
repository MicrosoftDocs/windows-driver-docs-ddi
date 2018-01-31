---
UID: NE:wwan._WWAN_SMS_FLAG
title: "_WWAN_SMS_FLAG"
author: windows-driver-content
description: The WWAN_SMS_FLAG enumeration lists different flags to filter SMS text messages.
old-location: netvista\wwan_sms_flag.htm
old-project: netvista
ms.assetid: 6620d6c8-2b8a-440e-acf4-fb08570b13bf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/PWWAN_SMS_FLAG, PWWAN_SMS_FLAG enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_FLAG enumeration [Network Drivers Starting with Windows Vista], wwan/WwanSmsFlagDraft, netvista.wwan_sms_flag, wwan/WWAN_SMS_FLAG, wwan/WwanSmsFlagSent, *PWWAN_SMS_FLAG, wwan/WwanSmsFlagIndex, WwanRef_379a284f-534f-4acb-88c7-d60f7627ab32.xml, wwan/WwanSmsFlagAll, PWWAN_SMS_FLAG, wwan/WwanSmsFlagNew, WwanSmsFlagAll, WWAN_SMS_FLAG, WwanSmsFlagNew, WwanSmsFlagIndex, WwanSmsFlagMax, WwanSmsFlagDraft, WwanSmsFlagSent, WwanSmsFlagOld, wwan/WwanSmsFlagOld, wwan/WwanSmsFlagMax, _WWAN_SMS_FLAG
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
-	WWAN_SMS_FLAG
product: Windows
targetos: Windows
req.typenames: WWAN_SMS_FLAG, *PWWAN_SMS_FLAG
req.product: Windows 10 or later.
---

# _WWAN_SMS_FLAG enumeration


## -description


The WWAN_SMS_FLAG enumeration lists different flags to filter SMS text messages.


## -syntax


````
typedef enum _WWAN_SMS_FLAG { 
  WwanSmsFlagAll    = 0,
  WwanSmsFlagIndex,
  WwanSmsFlagNew,
  WwanSmsFlagOld,
  WwanSmsFlagSent,
  WwanSmsFlagDraft,
  WwanSmsFlagMax
} WWAN_SMS_FLAG, *PWWAN_SMS_FLAG;
````


## -enum-fields




#### - WwanSmsFlagAll

No filter is set.


#### - WwanSmsFlagIndex

Filter based on the value of an index.


#### - WwanSmsFlagNew

Filter for new (unread) messages.


#### - WwanSmsFlagOld

Filter for old (read) messages.


#### - WwanSmsFlagSent

Filter for sent messages.


#### - WwanSmsFlagDraft

Filter for draft messages.


#### - WwanSmsFlagMax

The total number of filter flags.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_sms_filter.md">WWAN_SMS_FILTER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_FLAG enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

