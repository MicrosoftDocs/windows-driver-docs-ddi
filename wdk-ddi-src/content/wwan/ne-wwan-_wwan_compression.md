---
UID: NE:wwan._WWAN_COMPRESSION
title: "_WWAN_COMPRESSION"
author: windows-driver-content
description: The WWAN_COMPRESSION enumeration lists the different compression options that are supported by the MB device.
old-location: netvista\wwan_compression.htm
old-project: netvista
ms.assetid: a22bcf4e-f460-4f32-9e1e-4ae952fc87d0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_COMPRESSION, PWWAN_COMPRESSION, PWWAN_COMPRESSION enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_COMPRESSION, WWAN_COMPRESSION enumeration [Network Drivers Starting with Windows Vista], WwanCompressionEnable, WwanCompressionMax, WwanCompressionNone, WwanRef_ee5377b4-3352-4daf-96a4-296ad130a6f5.xml, _WWAN_COMPRESSION, netvista.wwan_compression, wwan/PWWAN_COMPRESSION, wwan/WWAN_COMPRESSION, wwan/WwanCompressionEnable, wwan/WwanCompressionMax, wwan/WwanCompressionNone"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_COMPRESSION
product: Windows
targetos: Windows
req.typenames: WWAN_COMPRESSION, *PWWAN_COMPRESSION
req.product: Windows 10 or later.
---

# _WWAN_COMPRESSION enumeration


## -description


The WWAN_COMPRESSION enumeration lists the different compression options that are supported by the MB
  device.


## -enum-fields




### -field WwanCompressionNone

No compression is applied.


### -field WwanCompressionEnable

Enable header and data compression.


### -field WwanCompressionMax

The total number of supported compression options.


## -remarks



This enumeration applies only to GSM devices. The MB Service specifies 
    <b>WwanCompressionNone</b> as the compression type for CDMA-based devices.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571201">WWAN_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571235">WWAN_SET_CONTEXT_STATE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_COMPRESSION enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

