---
UID: NE:wwan._WWAN_COMPRESSION
title: _WWAN_COMPRESSION (wwan.h)
description: The WWAN_COMPRESSION enumeration lists the different compression options that are supported by the MB device.
old-location: netvista\wwan_compression.htm
tech.root: netvista
ms.assetid: a22bcf4e-f460-4f32-9e1e-4ae952fc87d0
ms.date: 05/02/2018
keywords: ["WWAN_COMPRESSION enumeration"]
ms.keywords: "*PWWAN_COMPRESSION, PWWAN_COMPRESSION, PWWAN_COMPRESSION enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_COMPRESSION, WWAN_COMPRESSION enumeration [Network Drivers Starting with Windows Vista], WwanCompressionEnable, WwanCompressionMax, WwanCompressionNone, WwanRef_ee5377b4-3352-4daf-96a4-296ad130a6f5.xml, _WWAN_COMPRESSION, netvista.wwan_compression, wwan/PWWAN_COMPRESSION, wwan/WWAN_COMPRESSION, wwan/WwanCompressionEnable, wwan/WwanCompressionMax, wwan/WwanCompressionNone"
f1_keywords:
 - "wwan/WWAN_COMPRESSION"
 - "WWAN_COMPRESSION"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_COMPRESSION
targetos: Windows
req.typenames: WWAN_COMPRESSION, *PWWAN_COMPRESSION
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_context">WWAN_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_set_context_state">WWAN_SET_CONTEXT_STATE</a>
 

 

