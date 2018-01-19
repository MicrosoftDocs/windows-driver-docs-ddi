---
UID: NF:upssvc.UPSGetState
title: UPSGetState function
author: windows-driver-content
description: The UPSGetState function returns the operational state of the UPS.
old-location: battery\upsgetstate.htm
old-project: battery
ms.assetid: c60284ff-ebbd-455d-949c-e6d31ce65d5d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: UPSGetState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: upssvc.h
req.include-header: Upssvc.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UPSGetState
req.alt-loc: Upssvc.h
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
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# UPSGetState function



## -description
The <b>UPSGetState</b> function returns the operational state of the UPS.



## -syntax

````
DWORD UPSGetState(
   void 
);
````


## -parameters

### -param  

None


## -returns
The <b>UPSGetState</b> function returns one of the following DWORD values:
<dl>
<dt><b>UPS_ONLINE </b></dt>
</dl>Utility-supplied power is normal.
<dl>
<dt><b>UPS_ONBATTERY</b></dt>
</dl>Utility-supplied power is inadequate, and the UPS batteries are discharging.
<dl>
<dt><b>UPS_LOWBATTERY</b></dt>
</dl>Utility-supplied power is inadequate, and the UPS batteries are critically low.
<dl>
<dt><b>UPS_NOCOMM</b></dt>
</dl>Communication with the UPS is not currently established.

 


## -remarks
This is a nonblocking call. </p>