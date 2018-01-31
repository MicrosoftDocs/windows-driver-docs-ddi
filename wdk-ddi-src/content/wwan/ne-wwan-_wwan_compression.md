---
UID: NE:wwan._WWAN_COMPRESSION
title: "_WWAN_COMPRESSION"
author: windows-driver-content
description: The WWAN_COMPRESSION enumeration lists the different compression options that are supported by the MB device.
old-location: netvista\wwan_compression.htm
old-project: netvista
ms.assetid: a22bcf4e-f460-4f32-9e1e-4ae952fc87d0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PWWAN_COMPRESSION enumeration pointer [Network Drivers Starting with Windows Vista], _WWAN_COMPRESSION, netvista.wwan_compression, wwan/WwanCompressionMax, wwan/WwanCompressionNone, WWAN_COMPRESSION, *PWWAN_COMPRESSION, WwanCompressionEnable, WwanCompressionMax, WwanCompressionNone, wwan/WwanCompressionEnable, WwanRef_ee5377b4-3352-4daf-96a4-296ad130a6f5.xml, PWWAN_COMPRESSION, wwan/PWWAN_COMPRESSION, WWAN_COMPRESSION enumeration [Network Drivers Starting with Windows Vista], wwan/WWAN_COMPRESSION
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
-	WWAN_COMPRESSION
product: Windows
targetos: Windows
req.typenames: "*PWWAN_COMPRESSION, WWAN_COMPRESSION"
req.product: Windows 10 or later.
---

# _WWAN_COMPRESSION enumeration


## -description


The WWAN_COMPRESSION enumeration lists the different compression options that are supported by the MB
  device.


## -syntax


````
typedef enum _WWAN_COMPRESSION { 
  WwanCompressionNone    = 0,
  WwanCompressionEnable,
  WwanCompressionMax
} WWAN_COMPRESSION, *PWWAN_COMPRESSION;
````


## -enum-fields




#### - WwanCompressionNone

No compression is applied.


#### - WwanCompressionEnable

Enable header and data compression.


#### - WwanCompressionMax

The total number of supported compression options.


## -remarks


This enumeration applies only to GSM devices. The MB Service specifies 
    <b>WwanCompressionNone</b> as the compression type for CDMA-based devices.



## -see-also

<a href="..\wwan\ns-wwan-_wwan_set_context_state.md">WWAN_SET_CONTEXT_STATE</a>

<a href="..\wwan\ns-wwan-_wwan_context.md">WWAN_CONTEXT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_COMPRESSION enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

