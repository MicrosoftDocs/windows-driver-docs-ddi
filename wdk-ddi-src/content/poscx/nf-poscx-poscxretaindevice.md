---
UID: NF:poscx.PosCxRetainDevice
title: PosCxRetainDevice function
author: windows-driver-content
description: PosCxRetainDevice is called to extend the ownership of the device.
old-location: pos\poscxretaindevice.htm
old-project: pos
ms.assetid: 0DF5E1DA-35BA-406A-A708-461534373F12
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PosCxRetainDevice
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
req.alt-api: PosCxRetainDevice
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

# PosCxRetainDevice function



## -description
PosCxRetainDevice is called to extend the ownership of the device.



## -syntax

````
NTSTATUS PosCxRetainDevice(
  _In_ WDFDEVICE  device,
  _In_ WDFREQUEST request
);
````


## -parameters

### -param device [in]

A handle to a framework device object that represents the device.


### -param request [in]

A handle to a framework request object that represents the request. This request must come from a WDF IO queue. The caller must always complete the request.


## -returns
Possible return values are:

 


## -remarks
