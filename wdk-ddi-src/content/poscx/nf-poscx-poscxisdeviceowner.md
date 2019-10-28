---
UID: NF:poscx.PosCxIsDeviceOwner
title: PosCxIsDeviceOwner function (poscx.h)
description: PosCxIsDeviceOwner checks if the caller currently owns the claim on the device.
old-location: pos\poscxisdeviceowner.htm
tech.root: pos
ms.assetid: 48D30A9D-3BA2-4929-865A-D9A34DC6E497
ms.date: 02/23/2018
ms.keywords: PosCxIsDeviceOwner, PosCxIsDeviceOwner function, pos.poscxisdeviceowner, poscx/PosCxIsDeviceOwner
ms.topic: function
f1_keywords:
 - "poscx/PosCxIsDeviceOwner"
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
- PosCxIsDeviceOwner
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxIsDeviceOwner function


## -description


PosCxIsDeviceOwner checks if the caller currently owns the claim on the device.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param fileObject [in]

      A handle to a framework file object that identifies the caller, usually acquired with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetfileobject">WdfRequestGetFileObject</a>. If this parameter is NULL, <b>PosCxIsDeviceOwner</b> returns TRUE if the device is not currently owned.


## -returns



Returns TRUE if the caller is the device owner, or if <i>fileObject</i> is NULL and the device is not currently owned.

Otherwise, returns FALSE.



