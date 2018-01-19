---
UID: NF:poscx.PosCxClaimDevice
title: PosCxClaimDevice function
author: windows-driver-content
description: PosCxClaimDevice is called to claim a device for exclusive use. The caller should call PosCxReleaseDevice when the device is no longer needed.
old-location: pos\poscxclaimdevice.htm
old-project: pos
ms.assetid: 16EB583C-FB61-4811-A691-3FBD159F8FD0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PosCxClaimDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PosCxClaimDevice
req.alt-loc: poscx.h
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
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# PosCxClaimDevice function



## -description
PosCxClaimDevice is called to claim a device for exclusive use. 

The caller should call <a href="..\poscx\nf-poscx-poscxreleasedevice.md">PosCxReleaseDevice</a> when the device is no longer needed. 

      

If the device is already claimed, the caller must wait until access is granted.



## -syntax

````
NTSTATUS PosCxClaimDevice(
  _In_ WDFDEVICE  device,
  _In_ WDFREQUEST request
);
````


## -parameters

### -param device [in]

A handle to a framework device object that represents the device.


### -param request [in]

A handle to a framework request object that represents the request. This request must come from a WDF IO queue.


## -returns
Possible return values are:

 


## -remarks
