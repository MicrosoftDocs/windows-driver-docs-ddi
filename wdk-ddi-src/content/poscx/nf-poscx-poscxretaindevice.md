---
UID: NF:poscx.PosCxRetainDevice
title: PosCxRetainDevice function (poscx.h)
description: PosCxRetainDevice is called to extend the ownership of the device.
tech.root: pos
ms.date: 03/07/2023
keywords: ["PosCxRetainDevice function"]
ms.keywords: PosCxRetainDevice, PosCxRetainDevice function, pos.poscxretaindevice, poscx/PosCxRetainDevice
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PosCxRetainDevice
 - poscx/PosCxRetainDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxRetainDevice
---

## -description

PosCxRetainDevice is called to extend the ownership of the device.

## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param request [in]

A handle to a framework request object that represents the request. This request must come from a WDF IO queue. The caller must always complete the request.

## -returns

Possible return values are:

| Value | Description |
|---|---|
| **STATUS_SUCCESS** | The device was retained successfully. |
| **STATUS_ACCESS_DENIED** | The calling thread is not the owner of the device. |
| **STATUS_DEVICE_NOT_READY** | The PosCx library was not successfully initialized. |
