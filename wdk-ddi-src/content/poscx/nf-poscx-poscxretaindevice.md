---
UID: NF:poscx.PosCxRetainDevice
title: PosCxRetainDevice function (poscx.h)
description: PosCxRetainDevice is called to extend the ownership of the device.
old-location: pos\poscxretaindevice.htm
tech.root: pos
ms.assetid: 0DF5E1DA-35BA-406A-A708-461534373F12
ms.date: 02/23/2018
keywords: ["PosCxRetainDevice function"]
ms.keywords: PosCxRetainDevice, PosCxRetainDevice function, pos.poscxretaindevice, poscx/PosCxRetainDevice
f1_keywords:
 - "poscx/PosCxRetainDevice"
 - "PosCxRetainDevice"
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- poscx.h
api_name:
- PosCxRetainDevice
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxRetainDevice function


## -description


PosCxRetainDevice is called to extend the ownership of the device.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param request [in]

A handle to a framework request object that represents the request. This request must come from a WDF IO queue. The caller must always complete the request.


## -returns



Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>The device was retained successfully.</td>
</tr>
<tr>
<td><b>STATUS_ACCESS_DENIED</b></td>
<td>The calling thread is not the owner of the device.</td>
</tr>
<tr>
<td><b>STATUS_DEVICE_NOT_READY</b></td>
<td>The PosCx library was not successfully initialized.</td>
</tr>
</table>
 



