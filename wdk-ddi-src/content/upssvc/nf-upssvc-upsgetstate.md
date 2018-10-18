---
UID: NF:upssvc.UPSGetState
title: UPSGetState function
author: windows-driver-content
description: The UPSGetState function returns the operational state of the UPS.
old-location: battery\upsgetstate.htm
tech.root: battery
ms.assetid: c60284ff-ebbd-455d-949c-e6d31ce65d5d
ms.date: 2/15/2018
ms.keywords: UPSGetState, UPSGetState function [Battery Devices], UPS_fns_27023786-6c6e-43fe-96cb-0f298fec5ff1.xml, battery.upsgetstate, upssvc/UPSGetState
ms.topic: function
req.header: upssvc.h
req.include-header: Upssvc.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
-	Upssvc.h
api_name:
-	UPSGetState
product:
- Windows
targetos: Windows
req.typenames: 
---

# UPSGetState function


## -description


The <b>UPSGetState</b> function returns the operational state of the UPS.


## -parameters








## -returns



The <b>UPSGetState</b> function returns one of the following DWORD values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>UPS_ONLINE </b></dt>
</dl>
</td>
<td width="60%">
Utility-supplied power is normal.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>UPS_ONBATTERY</b></dt>
</dl>
</td>
<td width="60%">
Utility-supplied power is inadequate, and the UPS batteries are discharging.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>UPS_LOWBATTERY</b></dt>
</dl>
</td>
<td width="60%">
Utility-supplied power is inadequate, and the UPS batteries are critically low.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>UPS_NOCOMM</b></dt>
</dl>
</td>
<td width="60%">
Communication with the UPS is not currently established.

</td>
</tr>
</table>
 




## -remarks



This is a nonblocking call. 



